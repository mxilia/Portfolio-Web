<script setup>

const props = defineProps({
    img_path: String,
    name: String,
    time_text: String,
    type: String,
    desc: Array
})

</script>

<template>
    <div>
        <div class="flex gap-5 mb-10">
            <img :src="props.img_path" class="mt-1 h-16 w-16 border-2 border-white rounded-4xl">
            <div class="block"> 
                <div class="text-neutral-400"> {{ props.type }} </div>
                <div class="text-lg m-0"> {{ props.name }} </div>
                <div class="text-neutral-400"> {{ props.time_text }} </div>
                <div v-for="text in props.desc" :key="text" class="text-neutral-200">• {{ text }} </div>
            </div>
        </div>
    </div>
</template>

<style>
@import "tailwindcss";

</style>