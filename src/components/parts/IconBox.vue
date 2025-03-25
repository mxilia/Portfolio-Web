<script setup>

const props = defineProps({
  img_path: String
})


</script>

<template>
    <div class="flex justify-center items-center border-2 border-white rounded-xl w-10 h-10">
      <img class="w-5 h-5" :src="img_path">
    </div>
</template>

<style lang="css" scoped>
</style>