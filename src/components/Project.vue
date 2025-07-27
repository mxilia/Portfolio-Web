<script setup>
import TopicText from './parts/TopicText.vue';
import ProjectDiv from './parts/ProjectDiv.vue';
</script>

<template>
    <div id="project" class="flex flex-col items-center max-w-screen pt-20">
        <TopicText :text="'Project'" />
        <div class="dynamic-grid">
            <ProjectDiv :img_path="'/src/assets/project/tile_editor.png'" 
                        :topic_text="'2D-Tile-Editor'" 
                        :text="'A simple program written in pure Java for designing 2D top down game\'s map.'" 
                        :tech-tags="['Java']"
            />
            <ProjectDiv :img_path="'/src/assets/project/snake_rl.png'" 
                        :topic_text="'Snake-RL'" 
                        :text="'Written in Python to train a Deep Q-Learning agent to be able to complete game of snake. The algorithm is implemented using pytorch.'" 
                        :tech-tags="['Python']"
            />
        </div>
    </div>
</template>

<style lang="css" scoped>
@import "tailwindcss";

.dynamic-grid {
    @apply grid grid-cols-4 gap-5 pt-10 w-10/12
}

@media(max-width: 1400px){
    .dynamic-grid {
        @apply grid grid-cols-3 gap-5 pt-10 w-10/12
    }
}

@media(max-width: 1000px){
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