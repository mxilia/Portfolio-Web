<script setup>
import TechTag from './TechTag.vue';
</script>

<template>
    <div class="flex flex-col items-center border-2 border-white p-5 w-75 h-115">
        <img class="w-70 h-50">
        <span class="w-full text-white">Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde quam doloremque deleniti sapiente molestiae consequuntur dolorem nobis iste, blanditiis eius ab, accusantium dolores laborum quisquam, itaque eveniet corrupti reprehenderit cum!</span>
        <div class="flex gap-0.5">
            <TechTag :text="'SQL'" />
            <TechTag :text="'Next.js'" />
            <TechTag :text="'Mango'" />
        </div>
    </div>
</template>

<style lang="css" scoped>
</style>