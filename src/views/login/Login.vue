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
      <div class="warpper__login-button" @click="handleLogin">登录</div>
      <div class="warpper__login-link" @click="handleRegisterClick">立即注册</div>
      <transition name="fade">
      <Toast v-if="show" :message="toastMessage"/>
      </transition>
  </div>
</template>

<script>
import { reactive, toRefs } from 'vue'
import { useRouter } from 'vue-router'
import { post } from '../../utils/request'
import Toast, { useToastEffect } from '../../components/Toast'

const useLoginEffect = (showToast) => {
  const data = reactive({ username: '', password: '' });
  const router = useRouter();
  const handleLogin = async () => {
    if (!data.username.trim().length || !data.password.trim().length) {
      showToast('请输入用户名和密码!');
      return;
    }
    try {
      const result = await post('api/user/login', {
        username: data.username,
        password: data.password
      });
      if (result?.errno === 0) {
        localStorage.isLogin = true;
        router.push({ name: 'Home' });
      } else {
        showToast('登录失败');
      }
    } catch (e) {
      showToast('请求失败');
    }
  }
  const { username, password } = toRefs(data);
  return { username, password, handleLogin }
}

const useRegisterEffect = () => {
  const router = useRouter();
  const handleRegisterClick = () => {
    router.push({ name: 'Register' });
  }
  return { handleRegisterClick }
}

export default {
  name: 'Login',
  components: { Toast },
  setup () {
    const { show, toastMessage, showToast } = useToastEffect();
    const { username, password, handleLogin } = useLoginEffect(showToast);
    const { handleRegisterClick } = useRegisterEffect();
    return {
      handleLogin,
      handleRegisterClick,
      username,
      password,
      show,
      toastMessage
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
    &__login-button {
        margin: .32rem .4rem .16rem .4rem;
        line-height: .48rem;
        background: $btn-bgColor;
        box-shadow: 0 .04rem .08rem 0 rgba(0,145,255,0.32);
        border-radius: .04rem;
        color: $bgColor;
        font-size: .16rem;
        text-align: center;
    }
    &__login-link {
        text-align: center;
        font-size: .14rem;
        color: $content-notice-fontcolor;
    }
}

</style>
