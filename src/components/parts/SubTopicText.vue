<script setup>

const props = defineProps({
  text: String
})

</script>

<template>
    <h1 class="text-2xl text-white font-semibold mb-3 w-300">{{ props.text }}</h1>
</template>

<style lang="css" scoped>
</style>