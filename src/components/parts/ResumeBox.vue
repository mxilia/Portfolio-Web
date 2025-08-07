<script setup>
</script>

<template>
    <div class="flex items-center justify-center gap-3.5 bg-neutral-950 border-2 border-neutral-400 rounded-xl box">
        <img class="pic invert-100" :src="'/icon/resume_logo.png'">
        <div class="text">Download My Resume</div>
    </div>
</template>

<style lang="css" scoped>
@import "tailwindcss";

.box {
    @apply w-49 h-10
}

.text {
    @apply text-xs font-extrabold
}

.pic {
    @apply w-6 h-6
}

@media(max-width: 500px){
    .box {
        @apply w-41 h-8
    }

    .text {
        font-size: 9px;
        @apply font-extrabold
    }

    .pic {
        @apply w-5 h-5
    }
}

</style>