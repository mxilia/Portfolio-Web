<script setup>
import TopicText from './parts/TopicText.vue';
import TechBox from './parts/TechBox.vue';
</script>

<template>
    <div class="flex flex-col items-center mt-20 max-w-screen h-300">
        <TopicText :text="'About'" />
        <h1 class="text-2xl text-white font-semibold w-300">Skills</h1>
        <div class="flex w-300 h-200">
            <TechBox :text="'Github'" :img_path="'/github_logo.png'"/>
            <TechBox :text="'Github'" :img_path="'/github_logo.png'"/>
            <TechBox :text="'Github'" :img_path="'/github_logo.png'"/>
            <TechBox :text="'Github'" :img_path="'/github_logo.png'"/>
        </div>
    </div>
</template>

<style lang="css" scoped>
</style>