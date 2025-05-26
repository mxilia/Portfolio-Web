<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const width = ref(window.innerWidth);
const height = ref(window.innerHeight);
const column = 20;
const row = ref(10);

function updateRatio() {
    let ratio = height.value/width.value
    row.value = Math.round(column*ratio)
    console.log(row.value + " " + column)
}

function updateWidth() {
    width.value = window.innerWidth
    updateRatio()
}

function updateHeight() {
    height.value = window.innerHeight
    updateRatio()
}

onMounted(() => {
    window.addEventListener('resize', updateWidth)
    window.addEventListener('resize', updateHeight)
    updateRatio()
});

onUnmounted(() => {
    window.removeEventListener('resize', updateWidth)
    window.removeEventListener('resize', updateHeight)
})
</script>

<template>
    <div id="container" onclick="" class="grid border-l-2 border-t-2 border-neutral-800 bg-neutral-950 max-w-screen h-screen grid-cols-20">
        <div v-for="i in row*column" :key="i" class="regular-cell"></div>
    </div>
</template>

<style>
@import "tailwindcss";

.row-cell {
    margin: 0;
    padding: 0;
}

.regular-cell {
    @apply border-r-2 border-b-2 border-neutral-800
}

.regular-cell:hover {
    @apply bg-neutral-200/20
}
</style>