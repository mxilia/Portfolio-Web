<script setup>

const props = defineProps({
    text: String,
    img_path: String,
    img_invert: Int8Array
})

</script>

<template>
    <div class="flex items-center gap-2.5 border-2 border-neutral-600 rounded-lg bg-neutral-950 w-37 h-14">
        <div class="flex justify-center items-center rounded bg-neutral-900 ml-3 w-9 h-9">
            <img class=" w-7 h-7" :class="{ invert: props.img_invert }" :src="props.img_path">
        </div>
        <div class="text-sm text-white z-20">{{ props.text }}</div>
    </div>
</template>

<style lang="css" scoped>
</style>