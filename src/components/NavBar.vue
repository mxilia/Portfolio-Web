<script setup>
import {onMounted, onUnmounted, ref} from 'vue';

const navbar_active = ref(true);
let prev_scroll = window.scrollY;

const scroll_handle = () => {
    const current_scroll = window.scrollY;
    const diff = Math.floor(Math.abs(current_scroll-prev_scroll));
    if(diff) navbar_active.value = !(current_scroll>prev_scroll);
    prev_scroll = current_scroll;
}

onMounted(() => {
    window.addEventListener("scroll", scroll_handle);
});

onUnmounted(()=>{
    window.removeEventListener("scroll", scroll_handle);
});
</script>

<template>
    <nav id="navbar" :class="{'navbar_down' : navbar_active, 'navbar_up' : !navbar_active,
        'top-5 fixed left-1/2 -translate-x-1/2 z-50 flex justify-around items-center text-white bg-gray-950 thin-white-border w-85 h-8.5' : true}"
        @click="navbar_active = true"
    >
        <a href="#container">
            <div class="line_hover">Home</div>
        </a>
        <a href="#about">
            <div class="line_hover">About</div>
        </a>
        <a href="#project">
            <div class="line_hover">Project</div>
        </a>
        <a href="#contact">
            <div class="line_hover">Contact</div>
        </a>
    </nav>
</template>

<style lang="css" scoped>

.navbar_up {
    transform: translateY(-70px);
    transition: all 500ms ease-in-out;
    will-change: transform;
}

.navbar_down {
    transform: translateY(0);
    transition: all 500ms ease-in-out;
    will-change: transform;
}

.line_hover{
    transition: scale 250ms ease-in-out;
}

.line_hover:hover{
    scale: 1.2
}
</style>