<script lang="ts" setup>
import { ref, reactive } from "vue";
import TabList from "./components/TabList.vue"

// 创建一个变量记录选项卡状态
const current = ref(0) // 0表示球员。1 表示球队

const players = reactive([
  {
    name: "甘雨",
    img: "/images/gy.jpeg",
    rate: 1,
    hot: 43390
  },
  {
    name: "霄宫",
    img: "/images/xg.jpeg",
    rate: 2,
    hot: 33390
  },
  {
    name: "莫娜",
    img: "/images/mn.jpeg",
    rate: 3,
    hot: 23390
  }
])

const teams = reactive([
{
  name: "万叶",
  img: "/images/wy.jpeg",
  rate: 1,
  hot: 55555
},
  {
    name: "主角",
    img: "/images/zj.jpeg",
    rate: 2,
    hot: 33333
  },
  {
    name: "钟离",
    img: "/images/zl.jpeg",
    rate: 3,
    hot: 22222
  }
])

const playerMaxHot = players[0].hot
const teamMaxHot = teams[0].hot
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
        <TabList :items="players" :maxHot="playerMaxHot"></TabList>
      </div>
      <div v-show="current === 1">
        <TabList :items="teams" :maxHot="teamMaxHot"></TabList>
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

</style>
