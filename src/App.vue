<script lang="ts" setup>
import { ref, reactive } from "vue";
import Tab from "./components/Tab.vue"
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
  <Tab>
    <template #0>
      <TabList :items="players" :maxHot="playerMaxHot"></TabList>
    </template>
    <template v-slot:1>
      <TabList :items="teams" :maxHot="teamMaxHot"></TabList>
    </template>
  </Tab>
</template>

<style scoped>
</style>
