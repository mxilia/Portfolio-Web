<script setup>
import { ref, onMounted } from 'vue';

const width = window.innerWidth;
const height = window.innerHeight;
const column = 20;

const container = ref(null);

onMounted(() => {
    let ratio = height/width
    let row = Math.round(column*ratio);
    let array = Array(row).fill().map(() => Array(column).fill(undefined));
    for(let i=0;i<row;i++){
        for(let j=0;j<column;j++){
            array[i][j] = document.createElement('div');
            array[i][j].className = "regular-cell";
            container.value.appendChild(array[i][j]);
        }
    } 
});
</script>

<template>
    <div id="container" ref="container" onclick="" class="grid border-l-2 border-t-2 border-neutral-800 bg-neutral-950 max-w-screen h-screen grid-cols-20">
    </div>
</template>

<style>
@import "tailwindcss";

.regular-cell {
    @apply border-r-2 border-b-2 border-neutral-800
}

.regular-cell:hover {
    @apply bg-neutral-200/20
}
</style>