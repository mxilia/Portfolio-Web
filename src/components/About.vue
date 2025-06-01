<script setup>
import TopicText from './parts/TopicText.vue';
import SubTopicText from './parts/SubTopicText.vue';
import TechBox from './parts/TechBox.vue';
import HistoryDiv from './parts/HistoryDiv.vue';
</script>

<template>
    <div class="flex flex-col items-center mt-20 max-w-screen mb-10">
        <TopicText :text="'About'" />
        <SubTopicText :text="'Myself'" />
        <h1 class="text-neutral-200 w-10/12 mb-2">• Bronze Medalist in 20th TOI (Thailand Olympiad in Informatics).</h1>
        <h1 class="text-neutral-200 w-10/12 mb-2">• Currently studying Computer Science at Chulalongkorn University.</h1>
        <h1 class="text-neutral-200 w-10/12 mb-2">• Interested in Machine Learning.</h1>
        <SubTopicText class="mt-5" :text="'Technology'" />
        <div class="flex w-10/12 mb-5 gap-2 flex-wrap">
            <TechBox :text="'C'" :img_path="'/src/assets/icon/c_icon.png'"/>
            <TechBox :text="'C++'" :img_path="'/src/assets/icon/cpp_icon.png'"/>
            <TechBox :text="'Python'" :img_path="'/src/assets/icon/python_icon.png'"/>
            <TechBox :text="'Java'" :img_path="'/src/assets/icon/java_icon.png'"/>
            <TechBox :text="'JavaScript'" :img_path="'/src/assets/icon/javascript_icon.png'"/>
            <TechBox :text="'Vue'" :img_path="'/src/assets/icon/vue_icon.png'"/>
            <TechBox :text="'Github'" :img_invert="100" :img_path="'/src/assets/icon/github_logo.png'"/>
        </div>
        <SubTopicText :text="'Experience'" />
        <HistoryDiv />
    </div>
</template>

<style lang="css" scoped>
</style>