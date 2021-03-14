<template>
  <div class="warpper">
      <img class="warpper__img" src="http://www.dell-lee.com/imgs/vue3/user.png">
      <div class="warpper__input">
          <input
          class="warpper__input__content"
          placeholder="请输入用户名"
          v-model="username"/>
      </div>
      <div class="warpper__input">
          <input
          class="warpper__input__content"
          placeholder="请输入密码"
          type="password"
          v-model="password"/>
      </div>
      <div class="warpper__input">
          <input
          class="warpper__input__content"
          placeholder="确认密码"
          type="password"
          v-model="ensurement"/>
      </div>
      <div class="warpper__register-button" @click="handleRegister">注册</div>
      <div class="warpper__register-link" @click="handleLoginClick">已有账号，去登录</div>
      <transition name="fade">
      <Toast v-if="show" :message="toastMessage"/>
      </transition>
  </div>
</template>

<script>
import { useRouter } from 'vue-router'
import { reactive, toRefs } from 'vue'
import { post } from '../../utils/request.js'
import Toast, { useToastEffect } from '../../components/Toast'

const useRegisterEffect = (showToast) => {
  const data = reactive({
    username: '',
    password: '',
    ensurement: ''
  });
  const router = useRouter();
  const handleRegister = async () => {
    if (!data.username.trim().length || !data.password.trim().length) {
      showToast('请输入用户名和密码!');
      return;
    }
    if (ensurement !== password) {
      showToast('密码与确认密码不一致!');
      return;
    }
    try {
      const result = await post('api/user/register', {
        username: data.username,
        password: data.password
      });
      if (result?.errno === 0) {
        router.push({ name: 'Login' });
      } else {
        showToast('注册失败');
      }
    } catch (e) {
      showToast('请求失败');
    }
  }
  const { username, password, ensurement } = toRefs(data);
  return { username, password, ensurement, handleRegister }
}

const useLoginEffect = () => {
  const router = useRouter();
  const handleLoginClick = () => {
    router.push({ name: 'Login' });
  }
  return { handleLoginClick }
}

export default {
  name: 'Register',
  components: { Toast },
  setup () {
    const { show, toastMessage, showToast } = useToastEffect();
    const { username, password, ensurement, handleRegister } = useRegisterEffect(showToast);
    const { handleLoginClick } = useLoginEffect();
    return {
      show,
      toastMessage,
      username,
      password,
      ensurement,
      handleRegister,
      handleLoginClick
    }
  }
}
</script>

<style lang="scss" scoped>
@import '../../style/viriables.scss';

.warpper {
    position: absolute;
    top: 50%;
    left: 0;
    right: 0;
    transform: translateY(-50%);
    &__img {
        display: block;
        margin: 0 auto .4rem auto;
        width: .66rem;
        height: .66rem;
    }
    &__input {
        height: .48rem;
        margin: 0 .4rem .16rem .4rem;
        padding: 0 .16rem;
        background: #F9F9F9;
        border: 1px solid rgba(0,0,0,0.1);
        border-radius: .06rem;
        &__content{
            line-height: .48rem;
            border: none;
            outline: none;
            width: 100%;
            background: none;
            font-size: .16rem;
            &::placeholder {
                color: $content-notice-fontcolor;
            }
        }
    }
    &__register-button {
        margin: .32rem .4rem .16rem .4rem;
        line-height: .48rem;
        background: #0091FF;
        box-shadow: 0 .04rem .08rem 0 rgba(0,145,255,0.32);
        border-radius: .04rem;
        color: #FFF;
        font-size: .16rem;
        text-align: center;
    }
    &__register-link {
        text-align: center;
        font-size: .14rem;
        color: $content-notice-fontcolor;
    }
}

</style>
