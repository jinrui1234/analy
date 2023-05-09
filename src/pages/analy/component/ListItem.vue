<template>
  <div class="list-item" :key="list.id" v-for="list in menuList">
    <div :class="['list-submenu', list.selected ? 'showNext' : '']">
      <div
        class="list-meun-head"
        :style="{ 'padding-left': setPadding(zIndex) }"
        @click="shoNext(list)"
      >
        <wb-icon :icon="'video-analy-folder-icon'" class="folder-icon"></wb-icon>
        <div class="head-name">
          <span>{{ list.name }}</span>
        </div>
      </div>
      <list-item
        class="children"
        v-if="list.folders && list.folders.length > 0"
        :menuList="list.folders"
        :zIndex="getZindex()"
        :selectId="selectId"
      ></list-item>
    </div>
    <div class="list-menu-container">
      <div
        v-for="ipcId in list.ipcIds"
        :key="ipcId.ipcId"
        :class="['list-menu-item', ipcId.isEdit == 1 && ipcId.ipcId == selectId ? 'slected' : '']"
        :style="{ 'padding-left': setPadding(zIndex + 1) }"
        @click="itemClick(ipcId)"
      >
        <div class="publish-status" :style="getStatusColor(ipcId, zIndex)"></div>
        <span :style="getIpcNameStyle(ipcId)">{{ ipcId.ipcName }}</span>
        <el-tooltip effect="dark" :enterable="false" placement="right" :content="ipcId.publishMsg">
          <wb-icon
            icon="video-analy-abnormal"
            class="abnormal-icon"
            v-show="statusShow && ipcId.status != 1"
          />
        </el-tooltip>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { reactive } from 'vue'
const state = reactive({
  videoTitleTipShowBoolean: false,
})
const prop = defineProps({
  menuList: {
    type: Array,
    default: () => {
      return []
    },
  },
  zIndex: {
    type: Number,
    default: 0,
  },
  selectId: {
    type: [String, Number],
    default: '',
  },
})
// watch(() => foo, (newValue, oldValue) => {

// })
</script>

<style scoped lang="scss">
.list-item {
}
</style>