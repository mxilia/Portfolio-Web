<script setup>
import IconBox from './parts/IconBox.vue';
</script>

<template>
    <div class="flex justify-center items-center content-between max-w-screen h-screen">
        <img src="../assets/profile_pic.jpg" class="object-cover thin-white-border w-65 h-68">
        <div class="w-12 h-68"></div>
        <div class= "text-white h-68">
            <h1 class="text-6xl font-semibold">RAVINT<br>KOSOL</h1>
            <h1 class="text-2xl font-medium italic">Undergraduate</h1>
            <h1 class="text-1xl font-medium">➤ Thailand, Bangkok</h1>
            <div class="w-full h-5"></div>
            <div class="flex gap-3">
                <IconBox :img_path="'/catt.jpg'" />
                <IconBox :img_path="'/catt.jpg'" />
                <IconBox :img_path="'/catt.jpg'" />
                <IconBox :img_path="'/catt.jpg'" />
            </div>
        </div>
    </div>
</template>

<style lang="css" scoped>
</style>