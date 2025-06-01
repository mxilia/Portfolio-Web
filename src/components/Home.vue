<script setup>
import IconBox from './parts/IconBox.vue';
import ResumeBox from './parts/ResumeBox.vue';
import Background from './parts/Background.vue';
</script>

<template> 
    <div class="absolute top-1/2 left-1/2 -translate-1/2 flex justify-center items-center gap-8 content-between p-11">
        <img class="object-cover rounded-2xl border-1 border-neutral-400 w-65 h-70" src="../assets/cat.jpg">
        <div class= "flex flex-col gap-1.5 text-neutral-100 h-68">
            <div class="block">
                <h1 class="text-6xl font-semibold">RAVINT<br>KOSOL</h1>
                <h1 class="text-2xl text-neutral-300 font-medium italic">Undergraduate</h1>
                <h1 class="mb-2 text-1xl text-neutral-300 font-medium">➤ Thailand, Bangkok</h1>
            </div>
            <div class="flex flex-col gap-2">
                <ResumeBox />
                <div class="flex gap-3">
                    <IconBox :img_path="'/src/assets/icon/github_logo.png'" />
                    <IconBox :img_path="'/src/assets/icon/linkedin_logo.png'" />
                    <IconBox :img_path="'/src/assets/icon/mail_logo.png'" />
                    <IconBox :img_path="'/src/assets/icon/phone_logo.png'" />
                </div>
            </div>
        </div>
    </div>
    <Background />
</template>

<style lang="css" scoped>
</style>