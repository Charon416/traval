<template>
  <div class="home">
    <!-- <div class="top">弘源旅途</div> -->
    <nav-bar>
      <template #default>弘源旅途</template>
    </nav-bar>
    <div class="banner">
      <img src="@/assets/img/home/banner.webp" alt="">
    </div>
    <div class="location">
      <div class="city">广州</div>
      <div class="position">
        <span class="text">我的位置</span>
        <img src="@/assets/img/home/icon_location.png" alt="">
      </div>
    </div>
  </div>
</template>
<script setup>
import NavBar from '@/component/nav-bar/index.vue'

</script>

<style lang="less" scoped>
  .home {
    .top {
      height: 40px;
      line-height: 40px;
      text-align: center;
      font-size: 20px;
      color: var(--primary-color);
    }
    .banner {
      img {
        max-width: 100%;
      }
    }
    .location {
      height: 44px;
      display: flex;
      align-items: center;
      padding: 0 20px;
      .city {
        flex: 1;
      }
      .position {
        width: 80px;
        .text {
          font-size: 14px;
        }
        img {
          margin-left: 5px;
          width: 18px;
        }
      }
    }
  }
</style>