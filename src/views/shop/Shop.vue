<template>
  <div class="warpper">
    <div class="search">
      <div class="search__back iconfont"
       @click="handleBackClick"
      >&#xe60d;</div>
      <div class="search__content">
        <span class="search__content__icon iconfont">&#xe628;</span>
        <input class="search__content__input" placeholder="请输入商品名称">
      </div>
    </div>
    <ShopInfo :item="item" :hideBorder="true" v-if="item.imgUrl"/>
    <Content />
  </div>
</template>

<script>
import { reactive, toRefs } from 'vue'
import { useRouter, useRoute } from 'vue-router'
import { get } from '../../utils/request'
import ShopInfo from '../../components/ShopInfo'
import Content from './Content'

const useShopInfoEffect = () => {
  const route = useRoute();
  const data = reactive({ item: {} });
  const getItemData = async () => {
    const result = await get(`/api/shop/${route.params.id}`);
    if (result?.errno === 0 && result?.data) {
      data.item = result.data;
    }
  }
  const { item } = toRefs(data)
  return { item, getItemData }
}

const useBackRouterEffect = () => {
  const router = useRouter();
  const handleBackClick = () => {
    router.back();
  }
  return handleBackClick
}

export default {
  name: 'Shop',
  components: { ShopInfo, Content },
  setup () {
    const handleBackClick = useBackRouterEffect();
    const { item, getItemData } = useShopInfoEffect();
    getItemData();
    return { item, handleBackClick }
  }
}
</script>

<style lang="scss" scoped>
@import '../../style/viriables.scss';

  .warpper {
    padding: 0 .18rem;
  }

  .search {
    display: flex;
    margin: .14rem 0 .04rem 0;
    line-height: .32rem;
    &__back {
      width: .3rem;
      font-size: .24rem;
      color: #B6B6B6;
    }
    &__content {
      display: flex;
      flex: 1;
      background: $search-bgColor;
      border-radius: .16rem;
      &__icon {
        width: .44rem;
        text-align: center;
        color: $search-fontColor;
      }
      &__input {
        width: 100%;
        padding-right: .2rem;
        border: none;
        outline: none;
        background: none;
        height: .32rem;
        font-size: .14rem;
        color: $content-fontcolor;
        &::placeholder{
          color: $content-fontcolor;
        }
      }
    }
  }
</style>
