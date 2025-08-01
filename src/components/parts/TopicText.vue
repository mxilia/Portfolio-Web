<script setup>
import { onMounted, ref } from 'vue';

const props = defineProps({
  text: String
})

const topic_head = ref(null);
// WILL USE BETTER IMPLEMENTATION
onMounted(()=>{
	
});


</script>

<template>
    <div ref="topic_head" class="topic_head flex items-center text-white font-semibold text-4xl border-b-2 border-white mb-5 pb-3 w-10/12">{{ props.text }}</div>
</template>

<style lang="css" scoped>
@import "tailwindcss";

@keyframes appear {
	0% {
		opacity: 0;
	}
	100% {
		opacity: 1;
	}
}
</style>