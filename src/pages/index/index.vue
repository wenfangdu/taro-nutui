<script lang="ts" setup>
  import { ref } from 'vue'

  definePageConfig({
    disableSwipeBack: true,
  })

  const items = ref([1, 2, 3])
</script>

<template>
  <swiper style="height: 100vh">
    <swiper-item v-for="item in items" :key="item">
      <movable-area style="width: 100%; height: 100%">
        <movable-view
          style="width: 100%; height: 100%"
          direction="all"
          :scale="true"
          :scale-min="1"
        >
          <view class="item">{{ item }}</view>
        </movable-view>
      </movable-area>
    </swiper-item>
  </swiper>
</template>

<style lang="scss">
  .item {
    background: #09f;
    color: #fff;
    height: 100%;
    display: grid;
    place-items: center;
  }
</style>
