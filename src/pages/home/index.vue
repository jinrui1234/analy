<template>
  <div class="home">
    <div class="btn-box">
      <div class="btn" @click="goRouter('VideoAnaly')">视频分析</div>
    </div>
  </div>
</template>

<script setup>
import { useRouter } from 'vue-router'
const router = useRouter() // 声明路由实例
//路由跳转
const goRouter = (name) => {
  router.push({
    name: name,
    // query: flag && {
    //   solutionId: "1046850205366448128",
    // },
  })
}
</script>

<style lang="scss" scoped>
.home {
  width: 100%;
  height: 100%;
  background-image: url('@/assets/img/common/home.jpg');
  background-size: 100% 100%;
}
.btn-box {
  position: fixed;
  top: 20px;
  right: 30px;
  color: #ffffff;
  font-size: 14px;
  display: flex;
  .btn {
    line-height: 32px;
    width: 120px;
    border: 1px solid rgb(163, 164, 181);
    text-align: center;
    cursor: pointer;
    &:hover {
      color: rgba(163, 164, 181);
    }
  }
  .btn + .btn {
    margin-left: 15px;
  }
}
</style>
