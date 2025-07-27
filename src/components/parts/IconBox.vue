<script setup>

const props = defineProps({
	img_path: String
})

</script>

<template>
	<div class="flex justify-center items-center bg-neutral-950 border-2 border-neutral-400 rounded-xl box">
		<img class="g invert-100 pic" :src="props.img_path">
	</div>
</template>

<style lang="css" scoped>
@import "tailwindcss";

.box {
	@apply w-10 h-10
}

.pic {
	@apply h-4
}

@media(max-width: 500px){
	.box {
		@apply w-8 h-8
	}

	.pic {
		@apply h-3
	}
}
</style>