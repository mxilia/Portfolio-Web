<script setup>
import TopicText from './parts/TopicText.vue';
import SubTopicText from './parts/SubTopicText.vue';
import TechBox from './parts/TechBox.vue';
import HistoryDiv from './parts/HistoryDiv.vue';
</script>

<template>
    <div class="flex flex-col items-center mt-20 max-w-screen h-300">
        <TopicText :text="'About'" />
        <SubTopicText :text="'Stack'" />
        <div class="flex w-10/12 h-50">
            <TechBox :text="'Github'" :img_path="'/github_logo.png'"/>
            <TechBox :text="'Github'" :img_path="'/github_logo.png'"/>
            <TechBox :text="'Github'" :img_path="'/github_logo.png'"/>
            <TechBox :text="'Github'" :img_path="'/github_logo.png'"/>
        </div>
        <HistoryDiv />
    </div>
</template>

<style lang="css" scoped>
</style>