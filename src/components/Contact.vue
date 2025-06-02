<script setup>
import TopicText from './parts/TopicText.vue';
import ContactBox from './parts/ContactBox.vue';
</script>

<template>
    <div class="flex flex-col items-center mt-20 max-w-screen pb-20">
        <TopicText :text="'Contact'" />
        <div class="flex w-10/12 mb-5 gap-2 flex-wrap">
            <ContactBox :img_path="'/src/assets/icon/github_logo.png'" :img_invert="100" :text="'mxilia'"/>
        </div>
    </div>
</template>

<style lang="css" scoped>
</style>