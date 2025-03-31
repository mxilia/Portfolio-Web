<script setup>

const props = defineProps({
    text: String,
    img_path: String
})

</script>

<template>
    <div class="flex items-center gap-2.5 border-2 border-gray-100/15 rounded-lg bg-neutral-950 w-34 h-14">
        <div class="flex justify-center items-center rounded bg-neutral-900 ml-3 w-9 h-9">
            <img class="g invert-100 w-7 h-7" :src="props.img_path">
        </div>
        <div class="text-sm text-white">{{ props.text }}</div>
    </div>
</template>

<style lang="css" scoped>
</style>