<script setup>
import { ref } from 'vue';
import TopicText from './parts/TopicText.vue';
import ContactBox from './parts/ContactBox.vue';

const text = ['mxilia', 'ravintkosol@gmail.com'];
const img_name = ['github', 'gmail'];
const img_invert = [100, 0]
const img_height = [7, 7]
const on_tech = ref(false);

function enter_box(e) {
    on_tech.value = true;
    const highlight = document.getElementById("highlight2");
    const left = e.currentTarget.getBoundingClientRect().left;
    const top = e.currentTarget.getBoundingClientRect().top;
    const width = e.currentTarget.getBoundingClientRect().width;
    const container_left = e.currentTarget.parentElement.getBoundingClientRect().left;
    const container_top = e.currentTarget.parentElement.getBoundingClientRect().top;
    const offsetX = left-container_left;
    const offsetY = top-container_top;
    highlight.style.transform = `translate(${offsetX}px, ${offsetY}px)`;
    highlight.style.width= `${width}px`;
}

function leave_box() {
    on_tech.value = false;
}
</script>

<template>
    <div id="contact" class="flex flex-col items-center pt-20 max-w-screen">
        <TopicText :text="'Contact'" />
        <div class="flex w-10/12 mb-5 gap-2 flex-wrap" @mouseleave="leave_box">
            <div id="highlight2" @mouseleave="leave_box" :class="{'w-20 flex items-center gap-2.5 border-2 border-white rounded-lg bg-neutral-100 h-14 z-10 absolute' : true,
                          'inactive_box' : !on_tech,
                          'active_box': on_tech
                        }"
            ></div>
            <div v-for="(t, i) in text" :key="i" @mouseenter="enter_box">
                <ContactBox :img_path="'/src/assets/icon/'+img_name[i]+'_icon.png'" :img_height="img_height[i]" :img_invert="img_invert[i]" :text="t"/>
            </div>
        </div>
    </div>
</template>

<style lang="css" scoped>
.inactive_box {
    opacity: 0;
    z-index: -1;
    transition: all 100ms ease-out;
}

.active_box {
    opacity: 10%;
    transition: all 100ms ease-in-out;
}
</style>