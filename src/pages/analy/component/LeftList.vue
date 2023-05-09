<template>
  <div class="left-list__container">1111111</div>
</template>

<script setup lang="ts">
import { reactive } from 'vue'
const state = reactive({})
</script>

<style scoped lang="scss">
.left-list__container {
  width: 340px;
  height: 100%;
  background-color: #292c34;
  //   overflow: overlay;
  padding: 12px 0px;
  margin-right: 2px;
  border-bottom: 18px solid #292c34;
  flex-shrink: 0;
}
</style>