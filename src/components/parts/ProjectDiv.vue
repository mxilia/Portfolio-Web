<script setup>
import TechTag from './TechTag.vue';

const props = defineProps({
    img_path: String,
    topic_text: String,
    text: String,
    techTags: Array,
    info_path: String
})

</script>

<template>
    <div class="flex flex-col justify-between rounded-2xl border-2 border-neutral-400 w-full overflow-hidden">
        <div class="flex flex-col items-center w-full">
            <img class="w-full h-50 object-fit mb-2" :src="props.img_path">
            <h1 class="text-2xl text-white border-b-2 border-white font-semibold minus-width"> {{ props.topic_text }} </h1>
            <span class="w-full p-2 pl-5 text-neutral-200"> {{ props.text }}</span>
            <div class="flex flex-wrap gap-1 ml-10 w-full mb-2 pr-10">
                <TechTag v-for="tech in props.techTags" :key="tech" :text="tech" />
            </div>
        </div>
        <div class="flex flex-col items-center w-full mb-5">
            <div class="w-full ml-10 flex justify-end pr-10">
                <div class="bg-neutral-200 rounded-lg font-bold p-2 text-sm w-25 text-center">Learn More</div>
            </div>
        </div>
    </div>
</template>

<style lang="css" scoped>
.minus-width {
    width: -webkit-calc(100% - 40px);
}
</style>