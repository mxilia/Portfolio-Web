<script setup>

const props = defineProps({
    text: String
})

</script>

<template>
    <div class="flex items-center gap-2.5 border-2 border-gray-100/15 rounded-lg bg-neutral-950 pl-1.5 pr-1.5 h-7">
        <div class="text-sm text-white">{{ props.text }}</div>
    </div>
</template>

<style lang="css" scoped>
</style>