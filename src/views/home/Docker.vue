<template>
  <div class="docker">
    <div
      v-for="(item, index) in dockerList" :key="item.icon"
      :class="{'docker__item--active': index === 0}"
      class="docker__item"
    >
      <div class="iconfont" v-html="item.icon" />
      <div class="docker__title">{{item.text}}</div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Docker',
  setup () {
    const dockerList = [
      { icon: '&#xe9ce;', text: '首页' },
      { icon: '&#xe60a;', text: '购物车' },
      { icon: '&#xe613;', text: '订单' },
      { icon: '&#xe660;', text: '我的' }
    ]
    return { dockerList }
  }
}
</script>

<style lang="scss" scoped>
@import '../../style/viriables.scss';

.docker {
  display: flex;
  position: absolute;
  box-sizing: border-box;
  padding: 0 .18rem;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 0.49rem;
  border-top: .01rem solid $content-bgColor;
  color: $content-fontcolor;
  &__item {
    flex: 1;
    text-align: center;
    .iconfont {
      margin: .07rem 0 .02rem 0;
      font-size: .18rem;
    }
    &--active {
      color: #1FA4FC;
    }
  }
  &__title {
    font-size: .2rem;  //页面展示最低12px 想获取10px的展示效果的折中方案
    transform: scale(0.5,0.5);
    transform-origin: center top;
  }
}
</style>
