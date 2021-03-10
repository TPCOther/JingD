<template>
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
</template>

<script>
export default {
  name: 'StaticPart'
}
</script>

<style lang="scss">
@import '../../style/viriables.scss';
@import '../../style/mixins.scss';
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
</style>
