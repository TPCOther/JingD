<template>
  <div class="toast">{{ message }}</div>
</template>

<script>
import { reactive, toRefs } from 'vue'
export default {
  props: ['message']
}

export const useToastEffect = () => {
  const toastData = reactive({
    show: false,
    toastMessage: ''
  });
  const { show, toastMessage } = toRefs(toastData);
  const showToast = (message) => {
    toastData.toastMessage = message;
    toastData.show = true;
    setTimeout(() => {
      toastData.show = false;
      toastData.toastMessage = '';
    }, 2000);
  }
  return { show, toastMessage, showToast }
}
</script>

<style lang="scss" scoped>
@import '../style/viriables.scss';

.toast{
    position: fixed;
    left: 50%;
    top: 50%;
    transform: translate(-50%,-50%);
    padding: .1rem;
    background: rgba(0 , 0, 0, .35);
    border-radius: .05rem;
    color: $bgColor;
}

</style>
