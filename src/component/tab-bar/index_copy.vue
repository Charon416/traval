<template>
  <div class="tab-bar">
    <template v-for="item in tabbarData">
      <div class="tab-bar-item"  @click="tabClick(item)" :class="{ active: currentIndex === item.id }">
        <img v-show="item.id === currentIndex" :src="getAssetURL(item.img_active)" alt="">
        <img v-show="item.id !== currentIndex" :src="getAssetURL(item.img)" alt="">
        <span class="text">{{ item.title }}</span>
      </div>
    </template>
  </div>
</template>
<script setup>
import router from '@/router';
import { reactive, ref } from 'vue';

let currentIndex = ref(1)
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

const tabClick = (item) => {
  const { id, path } = item
  currentIndex.value = id
  router.push(path)
}

</script>

<style lang="less" scoped>
  .tab-bar {
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    height: 50px;
    display: flex;
    border-top: 1px solid #f3f3f3;

    .tab-bar-item {
      flex: 1;
      display: flex;
      flex-direction: column ;
      justify-content: center;
      align-items: center;
      &.active {
        color: var(--tab-color);
      }
      img {
        width: 28px;
      }
      .text {
        font-size: 14px;
      }

    }
  }
</style>