<template>
    <div class="analy-container">
      <LeftList/>
      <WorkSpace/>
    </div>
</template>

<script setup lang="ts">
import LeftList from "./component/LeftList.vue"
import WorkSpace from "./component/WorkSpace.vue"
</script>

<style scoped lang="scss">
.analy-container{
    height: 100%;
    width: 100%;
    user-select: none;
    background-color: #22242b;
    display: flex;
}
</style>