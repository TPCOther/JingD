<template>
  <div class="docker">
    <div class="docker__item docker__item--active">
      <div class="iconfont">&#xe9ce;</div>
      <div class="docker__title">首页</div>
      </div>
    <div class="docker__item">
      <div class="iconfont">&#xe60a;</div>
      <div class="docker__title">购物车</div>
      </div>
    <div class="docker__item">
      <div class="iconfont">&#xe613;</div>
      <div class="docker__title">订单</div>
      </div>
    <div class="docker__item">
      <div class="iconfont">&#xe660;</div>
      <div class="docker__title">我的</div>
      </div>
  </div>
</template>

<style lang="scss">
.docker {
  display: flex;
  position: absolute;
  box-sizing: border-box;
  padding: 0 .18rem;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 0.49rem;
  border-top: 1px solid #F1F1F1;
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
    font-size: 20px;  //页面展示最低12px 想获取10px的展示效果的折中方案
    transform: scale(0.5,0.5);
    transform-origin: center top;
  }
}
</style>
