<script lang="ts" setup>   
    import Photo from "./Photo.vue"
    import Hotbar from "./HotBar.vue"
    const props = defineProps(["item",'maxHot'])
    const item = props.item
    const maxHot = props.maxHot
    console.log(maxHot)
</script>

<template>
    <div class="tab-item">

        <Photo :src="item.img" :alt="item.name" :rate="item.rate"></Photo>
        <div class="desc">
            <span class="name">{{ item.name }}</span>
            <Hotbar :name="item.name" :hot="item.hot" :maxHot="maxHot"></Hotbar>
        </div>
        
    </div>
</template>

<style scoped>

.tab-item {
    display: flex;
    margin-bottom: 20px;
}

.desc {
    font-size: 30px;
    color: #fff;
    display: flex;
    flex-flow: column;
    justify-content: space-evenly;
    flex: auto;
    margin-left: 20px;
}

</style>