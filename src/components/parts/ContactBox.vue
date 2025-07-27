<script setup>

const props = defineProps({
    text: String,
    img_path: String,
    img_invert: Int8Array,
    img_height: Int16Array
})

</script>

<template>
    <div class="flex items-center gap-2.5 border-2 border-neutral-400 rounded-lg bg-neutral-950 pr-3 h-14">
        <div class="flex justify-center items-center rounded bg-neutral-900 ml-3 w-9 h-9">
            <img :class="['h-'+props.img_height, { invert: props.img_invert }]" :src="props.img_path">
        </div>
        <div class="text-sm text-white">{{ props.text }}</div>
    </div>
</template>

<style lang="css" scoped>
</style>