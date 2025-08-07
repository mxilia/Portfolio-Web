<script setup>
import { onMounted, ref } from 'vue';

const props = defineProps({
  text: String
})

</script>

<template>
    <div class="topic_head flex items-center text-white font-semibold text-4xl border-b-2 border-white mb-5 pb-3 w-10/12">{{ props.text }}</div>
</template>

<style lang="css" scoped>
@import "tailwindcss";
</style>