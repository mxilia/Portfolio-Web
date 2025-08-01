<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const width = ref(window.innerWidth);
const height = ref(window.innerHeight);
const column = 20;
const row = ref(10);
const pause = ref(false);
const grid = ref(Array.from({length: column*row.value}, () => Math.random() < 0.3));
const di=[0,0,1,-1,1,1,-1,-1];
const dj=[1,-1,0,0,1,-1,1,-1];
let interval = null;

function updateRatio() {
    let prev_row = row.value;
    let ratio = height.value/width.value;
    row.value = Math.round(column*ratio);
    if(prev_row != row.value) grid.value = Array.from({length: column*row.value}, () => Math.random() < 0.3);
}

function updateWidth() {
    width.value = window.innerWidth;
    updateRatio();
}

function updateHeight() {
    height.value = window.innerHeight;
    updateRatio();
}

function clicked(i) {
    grid.value[i] = !grid.value[i];
}

function toggle_pause() {
    pause.value = !pause.value;
    toggle_interval()
}

function toggle_interval() {
    if(pause.value){
        clearInterval(interval);
        interval = null;
    }
    else {
        interval = setInterval(()=>{
            let temp = [...grid.value];
            for(let i=0;i<temp.length;i++){
                let ci=Math.floor(i/column);
                let cj=i%column;
                let neighbor=0;
                for(let k=0;k<8;k++){
                    let ni=ci+di[k];
                    let nj=cj+dj[k];
                    if(ni<0 || nj<0 || ni>=row.value || nj>=column) continue;
                    if(temp[ni*column+nj]) neighbor++;
                }
                if(!temp[i] && neighbor==3) grid.value[i] = true;
                else if(temp[i] && neighbor<2) grid.value[i] = false;
                else if(temp[i] && neighbor>3) grid.value[i] = false;
            }
        }, 500);
    }
}

onMounted(() => {
    window.addEventListener('resize', updateWidth);
    window.addEventListener('resize', updateHeight);
    updateRatio();
    toggle_interval();
});

onUnmounted(() => {
    window.removeEventListener('resize', updateWidth);
    window.removeEventListener('resize', updateHeight);
    if(!pause.value) clearInterval(interval);
});
</script>

<template>
    <div id="container" class="grid border-l-2 border-t-2 border-neutral-800 bg-neutral-950 max-w-screen h-screen grid-cols-20">
        <div v-for="(cell, i) in grid" :key="i" @click="clicked(i)" :class="{'regular-cell' : cell, 'irregular-cell' : !cell}"></div>
    </div>
    <div class="max-w-screen text-white flex pl-1 pt-2">
        <div class="border-neutral-600 border-2 rounded-xl p-2 flex gap-0.5 flex-col justify-center items-center">
            <div>
                <div class="h-4.5 p-0.5">Game of life</div>
                <div class="text-sm text-neutral-400">John Conway</div>
            </div>
            <div class="p-1 flex gap-0.5 items-center">
                <div class="ibox">
                    <div class="pause"></div>
                </div>
                <div class="ibox" @click="toggle_pause">
                    <div :class="{'pause' : pause, 'play' : !pause}"></div>
                </div>
                <div class="ibox">
                    <div class="play"></div>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
@import "tailwindcss";

.row-cell {
    margin: 0;
    padding: 0;
}

.ibox {
    @apply w-7 h-7 border-neutral-400 border-2 rounded-xl flex items-center justify-center
}

.pause {
    transition: all 250ms ease-in-out;
    @apply border-l-14 border-b-[7px] border-t-[7px] border-y-transparent w-0 h-0 border-l-white ml-[2px]
}

.play {
    transition: all 250ms ease-in-out;
    @apply border-l-4 border-r-4 w-3 h-3
}

.regular-cell {
    transition: background-color 250ms ease-in-out;
    @apply border-r-2 border-b-2 bg-neutral-200/20
}

.irregular-cell {
    transition: background-color 250ms ease-in-out;
    @apply border-r-2 border-b-2 border-neutral-800
}

</style>