<script setup>
import TechTag from './TechTag.vue';

const props = defineProps({
    img_path: String,
    topic_text: String,
    text: String,
    techTags: Array,
    info_path: String,
    url_learn : String
})

</script>

<template>
    <div class="flex flex-col justify-between rounded-2xl border-2 border-neutral-400 w-full overflow-hidden">
        <div class="flex flex-col items-center w-full">
            <img class="w-full h-50 object-cover mb-2" :src="props.img_path">
            <h1 class="text-2xl text-white border-b-2 border-white font-semibold minus-width"> {{ props.topic_text }} </h1>
            <span class="w-full p-2 pl-5 text-neutral-200"> {{ props.text }}</span>
            <div class="flex flex-wrap gap-1 ml-10 w-full mb-2 pr-10">
                <TechTag v-for="tech in props.techTags" :key="tech" :text="tech" />
            </div>
        </div>
        <div class="flex flex-col items-center w-full mb-5">
            <a target="_blank" :href="props.url_learn">
                <div class="w-full ml-10 flex justify-end pl-5">
                    <div class="rounded-lg font-bold p-2 text-sm w-30 text-center animated-button">Learn More</div>
                </div>
            </a>
        </div>
    </div>
</template>

<style lang="css" scoped>
@import "tailwindcss";

.minus-width {
    width: -webkit-calc(100% - 40px);
}

.animated-button {
    background-color: var(--color-neutral-200);
    border-width: 2px;
    border-color: var(--color-neutral-200);
    color: var(--color-black);
    transition: background-color 300ms ease-in-out;
}

.animated-button:hover {
    background-color: var(--color-neutral-950);
    border-width: 2px;
    border-color: white;
    color: var(--color-white);
}

</style>