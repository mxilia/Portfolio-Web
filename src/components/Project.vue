<script setup>
import TopicText from './parts/TopicText.vue';
import ProjectDiv from './parts/ProjectDiv.vue';
</script>

<template>
    <div class="flex flex-col items-center max-w-screen h-300">
        <TopicText :text="'Project'" />
        <div class="flex flex-row flex-wrap items-center gap-10 pt-10 w-10/12">
            <ProjectDiv :img_path="'/src/assets/profile_pic.jpg'" :text="'Hello my friend i m hello my friend i m'" :tech-tags="['SQL','Java','Mango']"/>
            <ProjectDiv />
            <ProjectDiv />
            <ProjectDiv />
            <ProjectDiv />
            <ProjectDiv />
        </div>
    </div>
</template>

<style lang="css" scoped>
</style>