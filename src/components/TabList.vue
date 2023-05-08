<script setup lang="ts">
 const props = defineProps(["items","maxHot"])
 import TabItem from "./TabItem.vue"
</script>

<template>
    <div class="tab-list">
          <TabItem v-for="item in props.items" :item="item" :maxHot="props.maxHot"></TabItem>
        </div>
</template>

<style scoped>
.tab-list {
  margin: 20px;
}
</style>