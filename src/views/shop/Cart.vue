<template>
  <div class="cart">
    <div class="check">
        <div class="check__icon">
            <img src="http://www.dell-lee.com/imgs/vue3/basket.png"
             class="check__icon__img"/>
             <div class="check__icon__tag">1</div>
        </div>
        <div class="check__info">
            总计：<span class="check__info__price">&yen;127</span>
        </div>
        <div class="check__btn">
            去结算
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Cart'
}
</script>

<style lang="scss" scoped>
@import '../../style/viriables.scss';

.cart {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
}

.check {
  display: flex;
  height: .49rem;
  border-top: .01rem solid #F1F1F1;
  line-height: .49rem;
  &__icon {
    position: relative;
    width: .84rem;
    &__img {
      display: block;
      margin: .12rem auto;
      width: .28rem;
      height: .26rem;
    }
    &__tag {
      position: absolute;
      right: .2rem;
      top: .04rem;
      width: .2rem;
      height: .2rem;
      line-height: .2rem;
      background-color: $highlight-fontColor;
      border-radius: 50%;
      font-size: .12rem;
      text-align: center;
      color: #FFF;
      transform: scale(.5);
    }
  }
  &__info {
    flex: 1;
    color: $content-fontcolor;
    font-size: .12rem;
    &__price {
      color: $highlight-fontColor;
      font-size: .18rem;
    }
  }
  &__btn {
    width: .98rem;
    background-color: #4FB0F9;
    color: #FFF;
    font-size: .14rem;
    text-align: center;
  }
}

</style>
