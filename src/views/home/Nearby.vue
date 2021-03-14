<template>
  <div class="nearby">
      <h3 class="nearby__title">附近店铺</h3>
      <div
        v-for="item in nearbyList" :key="item._id"
        class="nearby__item"
      >
        <img :src="item.imgUrl" class="nearby__item__img">
        <div class="nearby__content">
          <div class="nearby__content__title">{{item.name}}</div>
          <div class="nearby__content__tags">
            <span class="nearby__content__tag">月售{{item.sales}}</span>
            <span class="nearby__content__tag">起送￥{{item.expressLimit}}</span>
            <span class="nearby__content__tag">运费￥{{item.expressPrice}}</span>
          </div>
          <p class="nearby__content__highlight">{{item.slogan}}</p>
        </div>
      </div>
    </div>
</template>

<script>
import { ref } from 'vue'
import { get } from '../../utils/request'

const useNearbyList = () => {
  const nearbyList = ref([]);
  const getNearbyList = async () => {
    try {
      const result = await get('api/shop/hot-list');
      if (result?.errno === 0 && result?.data?.length) {
        nearbyList.value = result.data
      } else {
        // showToast('获取失败');
      }
    } catch (e) {
      // showToast('请求失败');
    }
  }
  return { nearbyList, getNearbyList }
}
export default {
  name: 'Nearby',
  setup () {
    const { nearbyList, getNearbyList } = useNearbyList();
    getNearbyList();
    return { nearbyList }
  }
}
</script>

<style lang="scss" scoped>
@import '../../style/viriables.scss';

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
</style>
