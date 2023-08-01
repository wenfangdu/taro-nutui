<template>
  <scroll-view
    style="height: 500px; width: 100%; background-color: red"
    :scroll-y="true"
    :refresher-enabled="true"
    :refresher-threshold="100"
    :refresher-triggered="state.triggered"
    @refresherrefresh="onRefresh"
  ></scroll-view>
</template>

<script lang="ts" setup>
  import { reactive } from 'vue'

  const state = reactive({
    triggered: false,
  })

  const onRefresh = (): void => {
    state.triggered = true
    setTimeout(() => {
      state.triggered = false
    }, 2000)
  }
</script>
