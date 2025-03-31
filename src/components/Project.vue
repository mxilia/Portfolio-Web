<script setup>
import TopicText from './parts/TopicText.vue';
import ProjectDiv from './parts/ProjectDiv.vue';
</script>

<template>
    <div class="flex flex-col items-center max-w-screen h-300">
        <TopicText :text="'Project'" />
        <div class="flex flex-row flex-wrap items-center thin-white-border gap-10 p-20 w-300">
            <ProjectDiv />
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