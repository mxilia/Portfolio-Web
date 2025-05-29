<script setup>

const props = defineProps({
  text: String
})

</script>

<template>
    <div class="flex items-center text-white font-semibold text-4xl border-b-2 border-white mb-5 pb-3 w-10/12">{{ props.text }}</div>
</template>

<style lang="css" scoped>
</style>