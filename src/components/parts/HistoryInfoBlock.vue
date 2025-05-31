<script setup>

const props = defineProps({
  img_path: String,
  name: String,
  time_text: String
})

</script>

<template>
    <div>
        <div class="flex items-center gap-2">
            <img :src="props.img_path" class="h-16 w-16 border-2 border-white rounded-4xl">
            <div class="block"> 
                <div class="text-lg m-0"> {{ props.name }} </div>
                <div class="text-neutral-400"> {{ props.time_text }} </div>
            </div>
        </div>
    </div>
</template>

<style>
@import "tailwindcss";

</style>