<script setup>
import TopicText from './parts/TopicText.vue';
import ContactBox from './parts/ContactBox.vue';
</script>

<template>
    <div id="contact" class="flex flex-col items-center pt-20 max-w-screen">
        <TopicText :text="'Contact'" />
        <div class="flex w-10/12 mb-5 gap-2 flex-wrap">
            <ContactBox :img_path="'/src/assets/icon/github_logo.png'" :img_height="7" :img_invert="100" :text="'mxilia'"/>
            <ContactBox :img_path="'/src/assets/icon/gmail_logo.png'" :img_height="7" :img_invert="0" :text="'ravintkosol@gmail.com'"/>
        </div>
    </div>
</template>

<style lang="css" scoped>
</style>