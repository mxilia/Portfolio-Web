<script setup>
import { onMounted, ref } from 'vue';
import TopicText from './parts/TopicText.vue';
import SubTopicText from './parts/SubTopicText.vue';
import TechBox from './parts/TechBox.vue';
import HistoryDiv from './parts/HistoryDiv.vue';

const tech_name = ['C', 'C++', 'Python', 'Java', 'JavaScript', 'Vue', 'Git', 'Github']
const invert_val = [0, 0, 0, 0, 0, 0, 0, 100]
const on_tech = ref(false);

function enter_box(e) {
    on_tech.value = true;
    const highlight = document.getElementById("highlight");
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
    <div id="about" class="flex flex-col items-center pt-20 max-w-screen">
        <TopicText :text="'About'" />
        <SubTopicText :text="'Myself'" />
        <h1 class="text-neutral-200 w-10/12 mb-2">• Bronze Medalist in 20th TOI (Thailand Olympiad in Informatics).</h1>
        <h1 class="text-neutral-200 w-10/12 mb-2">• Currently studying Computer Science at Chulalongkorn University.</h1>
        <h1 class="text-neutral-200 w-10/12 mb-2">• Interested in Machine Learning.</h1>
        <SubTopicText class="mt-5" :text="'Technology'" />
        <div class="flex w-10/12 mb-5 gap-2 flex-wrap" @mouseleave="leave_box">
            <div id="highlight"  @mouseleave="leave_box" :class="{'flex items-center gap-2.5 border-2 border-white rounded-lg bg-neutral-100 w-37 h-14 z-10 absolute' : true,
                          'inactive_box' : !on_tech,
                          'active_box': on_tech
                        }"
            ></div>
            <div v-for="(name, i) in tech_name" :key="i" @mouseenter="enter_box">
                <TechBox :text="name" :img_invert="invert_val[i]" :img_path="'/icon/'+name.toLowerCase()+'_icon.png'" />
            </div>
        </div>
        <SubTopicText :text="'Experience'" />
        <HistoryDiv />
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