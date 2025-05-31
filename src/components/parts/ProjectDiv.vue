<script setup>
import TechTag from './TechTag.vue';

const props = defineProps({
    img_path: String,
    topic_text: String,
    text: String,
    techTags: Array
})

</script>

<template>
    <div class="flex flex-col items-center rounded-2xl border-2 border-neutral-400 w-full pb-5 overflow-hidden">
        <img class="w-full h-50 object-cover mb-2" :src="props.img_path">
        <h1 class="text-2xl text-white border-b-2 border-white font-semibold minus-width"> {{ props.topic_text }} </h1>
        <span class="w-full p-2 pl-5 text-white"> {{ props.text }}</span>
        <div class="flex gap-1 ml-10 w-full">
            <TechTag v-for="tech in props.techTags" :key="tech" :text="tech" />
        </div>
    </div>
</template>

<style lang="css" scoped>
.minus-width {
    width: -webkit-calc(100% - 40px);
}
</style>