<script setup>
import IconBox from './parts/IconBox.vue';
import ResumeBox from './parts/ResumeBox.vue';
import Background from './parts/Background.vue';
</script>

<template> 
    <div class="absolute top-1/2 left-1/2 -translate-1/2 flex justify-center items-center gap-8 content-between p-11">
        <img class="object-cover thin-white-border w-65 h-70" src="../assets/profile_pic.jpg">
        <div class= "flex flex-col gap-1.5 text-white h-68">
            <div class="block">
                <h1 class="text-6xl font-semibold">RAVINT<br>KOSOL</h1>
                <h1 class="text-2xl font-medium italic">Undergraduate</h1>
                <h1 class="mb-2 text-1xl font-medium">➤ Thailand, Bangkok</h1>
            </div>
            <div class="flex flex-col gap-2">
                <ResumeBox />
                <div class="flex gap-3">
                    <IconBox :img_path="'/github_logo.png'" />
                    <IconBox :img_path="'/linkedin_logo.png'" />
                    <IconBox :img_path="'/mail_logo.png'" />
                    <IconBox :img_path="'/phone_logo.png'" />
                </div>
            </div>
        </div>
    </div>
    <Background />
</template>

<style lang="css" scoped>
</style>