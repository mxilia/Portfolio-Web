<script setup>

const props = defineProps({
  text: String
})

</script>

<template>
    <h1 class="text-2xl text-white font-semibold mb-3 w-10/12">{{ props.text }}</h1>
</template>

<style lang="css" scoped>
</style>