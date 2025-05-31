<script setup>
import TopicText from './parts/TopicText.vue';
import ProjectDiv from './parts/ProjectDiv.vue';
</script>

<template>
    <div class="flex flex-col items-center max-w-screen">
        <TopicText :text="'Project'" />
        <div class="dynamic-grid">
            <ProjectDiv :img_path="'/src/assets/project/tile_editor.png'" :topic_text="'2D-Tile-Editor'" :text="'A simple program written in pure Java for designing 2D top down game\'s map.'" :tech-tags="['Java']"/>
        </div>
    </div>
</template>

<style lang="css" scoped>
@import "tailwindcss";

.dynamic-grid {
    @apply grid grid-cols-4 gap-5 pt-10 w-10/12
}

@media(max-width: 1200px){
    .dynamic-grid {
        @apply grid grid-cols-2 gap-5 pt-10 w-10/12
    }
}

@media(max-width: 650px){
    .dynamic-grid {
        @apply grid grid-cols-1 gap-5 pt-10 w-10/12
    }
}
</style>