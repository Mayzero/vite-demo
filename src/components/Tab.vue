<script lang="ts" setup>
import { ref, reactive } from "vue";


const current = ref(0) 
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
          <!-- <TabList :items="players" :maxHot="playerMaxHot"></TabList> -->
          <slot name="0"></slot>
        </div>
        <div v-show="current === 1">
          <!-- <TabList :items="teams" :maxHot="teamMaxHot"></TabList> -->
          <slot name="1"></slot>
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