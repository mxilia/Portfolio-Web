<script setup>

const props = defineProps({
	img_path: String,
	link: String
})

</script>

<template>
	<a :href="props.link" target="_blank">
		<div class="flex justify-center items-center bg-neutral-950 border-2 border-neutral-400 rounded-xl box">
			<img class="g invert-100 pic" :src="props.img_path">
		</div>
	</a>
</template>

<style lang="css" scoped>
@import "tailwindcss";

.box {
	transition: all 200ms ease-in-out;
	@apply w-10 h-10
}

.pic {
	@apply h-4
}

.box:hover {
	scale: 1.15;
	rotate: 20deg;
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