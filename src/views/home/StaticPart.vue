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
        <div
        v-for="item in staticList" :key="item.title"
        class="icons__item"
        >
          <img
            class="icons__item__img"
            :src="`http://www.dell-lee.com/imgs/vue3/${item.imgName}.png`"
          />
          <p class="icons__item__desc">{{item.title}}</p>
        </div>
    </div>
    <div class="gap"></div>
</template>

<script>
export default {
  name: 'StaticPart',
  setup () {
    const staticList = [
      { imgName: '超市', title: '超市便利' },
      { imgName: '菜市场', title: '菜市场' },
      { imgName: '水果店', title: '水果店' },
      { imgName: '鲜花', title: '鲜花绿植' },
      { imgName: '医药健康', title: '医药健康' },
      { imgName: '家居', title: '家居时尚' },
      { imgName: '蛋糕', title: '烘培蛋糕' },
      { imgName: '签到', title: '签到' },
      { imgName: '大牌免运', title: '大牌免运' },
      { imgName: '红包', title: '红包套餐' }
    ]
    return { staticList }
  }
}
</script>

<style lang="scss" scoped>
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
  background: $search-bgColor;
  color: $search-fontcolor;
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
