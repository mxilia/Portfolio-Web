<script setup>
import TechTag from './TechTag.vue';

const props = defineProps({
    img_path: String,
    text: String,
    techTags: Array
})

</script>

<template>
    <div class="flex flex-col items-center rounded-2xl border-2 border-neutral-400 w-75 pb-5 overflow-hidden">
        <img class="w-full h-50 object-cover mb-2" :src="props.img_path">
        <h1 class="text-2xl text-white font-semibold w-64">Bro</h1>
        <span class="w-full p-2 pl-5 text-white"> {{ props.text }}</span>
        <div class="flex gap-1 ml-10 w-full">
            <TechTag v-for="tech in props.techTags" :key="tech":text="tech" />
        </div>
    </div>
</template>

<style lang="css" scoped>
</style>