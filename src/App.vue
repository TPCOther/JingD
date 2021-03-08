<template>
  <div class="warpper">
    <div class="position">
      <span class="iconfont position__icon">&#xe64f;</span>
      北京理工大学国防科技园2号楼10层
      <span class="iconfont position__notice">&#xe7e5;</span>
    </div>
    <div class="search">
      <span class="iconfont">&#xe628;</span>
      山姆会员商店优惠商品
    </div>
    <div class="banner">
      <img class="banner__img" src="http://www.dell-lee.com/imgs/vue3/banner.jpg" />
    </div>
  </div>
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
@import './style/viriables.scss';
@import './style/mixins.scss';

.warpper {
  position: absolute;
  left: 0;
  top: 0;
  bottom: .5rem;
  right: 0;
  padding: 0 .18rem;
}

.position {
  position: relative;
  padding: .16rem .24rem .16rem 0;
  line-height: .22rem;
  font-size: .16rem;
  @include ellipsis;
  .position__icon {
    position: relative;
    top: .01rem;
    font-size: .2rem;
  }
  .position__notice {
    position: absolute;
    right: 0;
    top: .17rem;
    font-size: .2rem;
  }
  color: $content-fontcolor;
}

.search {
  margin-bottom: .12rem;
  line-height: .32rem;
  background: #F5F5F5;
  color: #B7B7B7;
  border-radius: .16rem;
  font-size: .14rem;
  .iconfont {
    position: relative;
    top: .02rem;
    font-size: .2rem;
    padding: 0 .08rem 0 .16rem;
    display: inline-block;
  }
}

.banner {
  height: 0;
  overflow: hidden;
  padding-bottom: 25.4%; //防止图片加载的时候占不满实际的空间
  &__img {
    width: 100%;
  }
}

.docker {
  display: flex;
  position: absolute;
  box-sizing: border-box;
  padding: 0 .18rem;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 0.49rem;
  border-top: .01rem solid #F1F1F1;
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
