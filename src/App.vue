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
    <div class="icons">
        <div class="icons__item">
          <img
            class="icons__item__img"
            src="http://www.dell-lee.com/imgs/vue3/超市.png"
          />
          <p class="icons__item__desc">超市便利</p>
        </div>
        <div class="icons__item">
          <img
            class="icons__item__img"
            src="http://www.dell-lee.com/imgs/vue3/菜市场.png"
          />
          <p class="icons__item__desc">菜市场</p>
        </div>
        <div class="icons__item">
          <img
            class="icons__item__img"
            src="http://www.dell-lee.com/imgs/vue3/水果店.png"
          />
          <p class="icons__item__desc">水果店</p>
        </div>
        <div class="icons__item">
          <img
            class="icons__item__img"
            src="http://www.dell-lee.com/imgs/vue3/鲜花.png"
          />
          <p class="icons__item__desc">鲜花绿植</p>
        </div>
        <div class="icons__item">
          <img
            class="icons__item__img"
            src="http://www.dell-lee.com/imgs/vue3/医药健康.png"
          />
          <p class="icons__item__desc">医药健康</p>
        </div>
        <div class="icons__item">
          <img
            class="icons__item__img"
            src="http://www.dell-lee.com/imgs/vue3/家居.png"
          />
          <p class="icons__item__desc">家居时尚</p>
        </div>
        <div class="icons__item">
          <img
            class="icons__item__img"
            src="http://www.dell-lee.com/imgs/vue3/蛋糕.png"
          />
          <p class="icons__item__desc">烘培蛋糕</p>
        </div>
        <div class="icons__item">
          <img
            class="icons__item__img"
            src="http://www.dell-lee.com/imgs/vue3/签到.png"
          />
          <p class="icons__item__desc">签到</p>
        </div>
        <div class="icons__item">
          <img
            class="icons__item__img"
            src="http://www.dell-lee.com/imgs/vue3/大牌免运.png"
          />
          <p class="icons__item__desc">大牌免运</p>
        </div>
        <div class="icons__item">
          <img
            class="icons__item__img"
            src="http://www.dell-lee.com/imgs/vue3/红包.png"
          />
          <p class="icons__item__desc">红包套餐</p>
        </div>
      </div>
    <div class="gap"></div>
    <div class="nearby">
      <h3 class="nearby__title">附近店铺</h3>
      <div class="nearby__item">
        <img src="http://www.dell-lee.com/imgs/vue3/near.png" class="nearby__item__img">
        <div class="nearby__content">
          <div class="nearby__content__title">沃尔玛</div>
          <div class="nearby__content__tags">
            <span class="nearby__content__tag">月售1万+</span>
            <span class="nearby__content__tag">月售1万+</span>
            <span class="nearby__content__tag">月售1万+</span>
          </div>
          <p class="nearby__content__highlight">VIP尊享满89元减4元运费</p>
        </div>
      </div>
      <div class="nearby__item">
        <img src="http://www.dell-lee.com/imgs/vue3/near.png" class="nearby__item__img">
        <div class="nearby__content">
          <div class="nearby__content__title">沃尔玛</div>
          <div class="nearby__content__tags">
            <span class="nearby__content__tag">月售1万+</span>
            <span class="nearby__content__tag">月售1万+</span>
            <span class="nearby__content__tag">月售1万+</span>
          </div>
          <p class="nearby__content__highlight">VIP尊享满89元减4元运费</p>
        </div>
      </div>
      <div class="nearby__item">
        <img src="http://www.dell-lee.com/imgs/vue3/near.png" class="nearby__item__img">
        <div class="nearby__content">
          <div class="nearby__content__title">沃尔玛</div>
          <div class="nearby__content__tags">
            <span class="nearby__content__tag">月售1万+</span>
            <span class="nearby__content__tag">月售1万+</span>
            <span class="nearby__content__tag">月售1万+</span>
          </div>
          <p class="nearby__content__highlight">VIP尊享满89元减4元运费</p>
        </div>
      </div>
      <div class="nearby__item">
        <img src="http://www.dell-lee.com/imgs/vue3/near.png" class="nearby__item__img">
        <div class="nearby__content">
          <div class="nearby__content__title">沃尔玛</div>
          <div class="nearby__content__tags">
            <span class="nearby__content__tag">月售1万+</span>
            <span class="nearby__content__tag">月售1万+</span>
            <span class="nearby__content__tag">月售1万+</span>
          </div>
          <p class="nearby__content__highlight">VIP尊享满89元减4元运费</p>
        </div>
      </div>
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
  overflow-y: auto;
  position: absolute;
  left: 0;
  top: 0;
  bottom: .5rem;
  right: 0;
  padding: 0 .18rem .2rem .18rem;
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

.icons {
  display: flex;
  flex-wrap: wrap;
  margin-top: .16rem;
  &__item {
    width: 20%;
    &__img {
      display: block;
      width: .4rem;
      height: .4rem;
      margin: 0 auto;
    }
    &__desc {
      text-align: center;
      margin: .06rem 0 .16rem 0;
      color: $content-fontcolor;
    }
  }
}

.gap {
  height: .1rem;
  background: $content-bgColor;
  margin: 0 -.18rem;
}

.nearby {
  &__title {
    margin: .16rem 0 .02rem 0;
    font-size: .18rem;
    font-weight: normal;
    color: $content-fontcolor;
  }
  &__item{
    display: flex;
    padding-top: .12rem;
    &__img {
      width: .56rem;
      height: .56rem;
      margin-right: .16rem;
    }
  }
  &__content {
    flex: 1;
    padding-bottom: .12rem;
    border-bottom: .01rem solid $content-bgColor;
    &__title {
      line-height: .22rem;
      font-size: .16rem;
      color: $content-fontcolor;
    }
    &__tags {
      margin-top: .08rem;
      line-height: .18rem;
      font-size: .13rem;
      color: $content-fontcolor;
    }
    &__tag {
      margin-right: .16rem;
    }
    &__highlight {
      margin: .08rem 0 0 0;
      line-height: .18rem;
      font-size: .13rem;
      color: #E93B3B;
    }
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
