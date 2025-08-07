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
const loop_play = ref(false);
const delete_play = ref(false);
const game_state = ref(true);
let interval = null;

function gen_grid(random_prop) {
    grid.value = Array.from({length: column*row.value}, () => Math.random() < random_prop);
}

function updateRatio() {
    let prev_row = row.value;
    let ratio = height.value/width.value;
    row.value = Math.round(column*ratio);
    if(prev_row != row.value) gen_grid(0.3);
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
    toggle_interval();
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
        }, 750);
    }
}

function loop_clicked() {
    loop_play.value=true;
    gen_grid(0.3);
}

function delete_clicked() {
    delete_play.value = true;
    gen_grid(0);
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
        <div class="box_transition border-neutral-600 border-2 rounded-xl p-2 flex gap-0.5 flex-col justify-center items-center" :class="{ 'move_box' : !game_state }">
            <div class="flex flex-col items-center">
                <div class="h-4.5 p-0.5">Game of life</div>
                <div class="text-sm text-neutral-400">John Conway</div>
                <div class="w-[90%] h-[3px] bg-white mt-1 mb-1">
                    <div :class="{'loading-stop' : pause, 'running_bar': !pause}"></div>
                </div>
            </div>
            <div class="p-1 flex gap-0.5 items-center">
                <div class="ibox" @click="loop_clicked">
                    <img 
                        :src="require('@/assets/icon/loop_icon.png')"
                        class="h-5 w-5 invert-100" 
                        :class="{'play_loop' : loop_play}"
                        @animationend="loop_play=false"
                    />
                </div>
                <div class="ibox" @click="toggle_pause">
                    <div :class="{'pause' : pause, 'play' : !pause}"></div>
                </div>
                <div class="ibox" @click="delete_clicked">
                    <img 
                        src="../../assets/icon/trash_icon.png"
                        class="h-4 w-4 invert-100"
                        :class="{'play_delete' : delete_play}"
                        @animationend="delete_play=false"
                    />
                </div>
            </div>
        </div>
        <div @click="game_state=!game_state" :class="{ 'move_box' : !game_state}" class="box_transition mt-2 flex items-center h-[100%] border-r-2 border-t-2 border-b-2 border-neutral-600 rounded-tr-[8px] rounded-br-[8px] pl-1 pr-1">
            <div v-if="game_state" class="arrow"> > </div>
            <div v-else class="arrow"> < </div>
        </div>
    </div>
</template>

<style>
@import "tailwindcss";

@keyframes loading {
    0% {
        width: 0%;
        left: 0%;
    }
    50% {
        width: 100%;
        left: 0%;
    }
    100% {
        width: 0%;
        left: 100%;
    }
}

@keyframes rotate {
    0% {
        transform: rotate(0deg);
    }
    100% {
        transform: rotate(180deg);
    }
}

@keyframes fade {
    0% {
        opacity: 1;
    }
    50% {
        opacity: 0;
    }
    100% {
        opacity: 1;
    }
}

.move_box {
    transform: translateX(-135px);
}

.box_transition {
    transition: all 600ms ease-in-out;
}

.arrow {
    user-select: none;
}

.play_delete {
    animation: fade 250ms ease-in-out;
}

.play_loop {
    animation: rotate 250ms linear;
}

.loading-stop {
    opacity: 0;
    transition: all 750ms linear;
    @apply h-[100%] bg-red-600 z-10 relative
}

.row-cell {
    margin: 0;
    padding: 0;
}

.ibox {
    @apply w-7 h-7 border-neutral-400 border-2 rounded-xl flex items-center justify-center
}

.running_bar {
    animation-name: loading;
    animation-duration: 750ms;
    animation-iteration-count: infinite;
    animation-timing-function: linear;
    transition: all 100ms linear;
    @apply h-[100%] bg-green-500 z-10 relative
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