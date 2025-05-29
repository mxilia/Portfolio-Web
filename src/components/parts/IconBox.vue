<script setup>

const props = defineProps({
  img_path: String
})

</script>

<template>
    <div class="flex justify-center items-center bg-neutral-950 border-2 border-neutral-400 rounded-xl w-10 h-10">
      <img class="g invert-100 h-4" :src="props.img_path">
    </div>
</template>

<style lang="css" scoped>
</style>