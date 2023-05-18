<template>
  <div class="tab-bar">
    <van-tabbar v-model="currentIndex" active-color="#ff9645">
      <template v-for="(item, index) in tabbarData">
        <van-tabbar-item :to="item.path">
          <template #default>
            <span>{{ item.title }}</span>
          </template>
          <template #icon>
            <img v-show="index === currentIndex" :src="getAssetURL(item.img_active)" alt="">
            <img v-show="index !== currentIndex" :src="getAssetURL(item.img)" alt="">
          </template>
        </van-tabbar-item>
      </template>
    </van-tabbar>
  </div>
</template>
<script setup>
import { reactive, ref } from 'vue';

let currentIndex = ref(0)
const tabbarData = reactive([
  {
    id: 1,
    title: '首页',
    img: 'home.png',
    img_active: 'home_active.png',
    path: '/home'
  },
  {
    id: 2,
    title: '收藏',
    img: 'favor.png',
    img_active: 'favor_active.png',
    path: '/favor'
  },
  {
    id: 3,
    title: '订单',
    img: 'order.png',
    img_active: 'order_active.png',
    path: '/order'
  },
  {
    id: 4,
    title: '消息',
    img: 'message.png',
    img_active: 'message_active.png',
    path: '/message'
  }
])
const getAssetURL = (image) => {
  // 参数一：相对路径
  return new URL(`../../assets/img/tabbar/${image}`, import.meta.url).href
}

</script>

<style lang="less" scoped>
.tab-bar {
  :deep(.van-tabbar-item__text) {
    font-size: 14px;
  }
  img {
    height: 26px;
  }
}
</style>