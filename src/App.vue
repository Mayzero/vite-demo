<script lang="ts" setup>
import { ref, reactive } from "vue";
import TabItem from "./components/TabItem.vue"

// 创建一个变量记录选项卡状态
const current = ref(0) // 0表示球员。1 表示球队
const player = reactive({
  name: "甘雨",
  img: "/images/gy.jpg",
  rate: 1,
  hot: "43390热度"
})

const team = reactive({
  name: "万叶",
  img: "/images/wy.jpeg",
  rate: 1,
  hot: "433热度"
})
</script>

<template>
  <div class="tab-wrapper">
    <!-- 选项卡头部 -->
    <header class="tab-head">
      <!-- 定义两个按钮 -->
      <div @click="current = 0" class="tab-button" :class="{ active: current === 0 }">热门球员</div>
      <div @click="current = 1" class="tab-button" :class="{ active: current === 1 }">热门球队</div>
    </header>
    <!-- 选项卡主体 -->
    <div class="main">
      <!-- 0 球员 1 球队 -->
      <div v-show="current === 0">
        <div class="tab-list">
          <TabItem :item="player"></TabItem>
        </div>
      </div>
      <div v-show="current === 1">
        <div class="tab-list">
          <TabItem :item="team"></TabItem>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.tab-wrapper {
  box-sizing: border-box;
  width: 800px;
  padding: 20px;
  background-color: rgb(45, 83, 211);
}

.tab-head {
  display: flex;
  border-radius: 10px;
  overflow: hidden;
}

.tab-button {
  background-color: #fff;
  font-size: 30px;
  padding: 10px 0;
  text-align: center;
  flex: auto;
  cursor: pointer;
  transition: 0.5s;
}

.tab-button:not(.active):hover {
  color: rgb(187, 3, 52);
}

.active {
  background-color: rgb(187, 3, 52);
  color: #fff;
}

.tab-list {
  margin: 20px;
}
</style>
