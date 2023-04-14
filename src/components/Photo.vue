<script lang="ts" setup>
    const props = defineProps(['src','alt','rate'])
</script>

<template>
    <div class="photo">
        <img :src="props.src" alt="props.alt">
        <span>{{ props.rate }}</span>
    </div>
</template>

<style scoped>
.photo {
    width: 150px;
    height: 150px;
    border-radius: 20px;
    overflow: hidden;
    position: relative;
}

.photo img {
    width: 100%;
    height: 100%;
    vertical-align: top;
}

.photo span {
    position: absolute;
    width: 40px;
    height: 40px;
    background-color: rgb(245, 102, 1);
    top: 0;
    left: 0;
    font-size: 20px;
    font-weight: bold;
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    border-bottom-right-radius: 20px;
}
</style>