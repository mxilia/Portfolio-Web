<script setup>
import HistoryInfoBlock from './HistoryInfoBlock.vue';

</script>

<template>
    <div class="w-10/12 text-white">
        <div class="flex items-center justify-between border-2 border-neutral-200 rounded-tl-2xl rounded-tr-2xl pl-1 pr-1 mb-2 h-10">
            <div class="text-center text-xl w-1/2 education-on">Education</div>
            <div class="text-center text-xl w-1/2">Work</div>
        </div>
        <div class="h-100 w-full border-2 border-neutral-500">
            <HistoryInfoBlock :name="'Chulalongkorn University'" :time_text="'2024 - now'" :img_path="'/src/assets/cat.jpg'" />
        </div>
        <div class="inactive">

        </div>
    </div>
</template>

<style>
@import "tailwindcss";

.inactive {
    display: none;
}

.education-on {
    border-radius: 12px 0px 0px 0px;
    @apply bg-white text-neutral-950
}

.work-on {
    border-radius: 0px 12px 0px 0px;
    @apply bg-white text-neutral-950
}
</style>