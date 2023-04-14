<script lang="ts" setup>   
    import Photo from "./Photo.vue"
    const props = defineProps(["item"])
    const item = props.item
</script>

<template>
    <div class="tab-item">

        <Photo :src="item.img" :alt="item.name" :rate="item.rate"></Photo>
        <div class="desc">
            <span class="name">{{item.name}}</span>
            <div class="hot-bar">
                <div class="inner">{{item.hot}}</div>
            </div>
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

.hot-bar {
    background-color: rgb(3, 37, 103);
    border-radius: 20px;
    text-indent: 0.5em;
}

.inner {
    background-color: red;
    border-radius: 20px;
    background-image: linear-gradient(to right, rgb(187, 3, 52) 50%, rgb(66, 2, 12));
    width: 10%;
    white-space: nowrap;
}
</style>