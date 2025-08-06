<script setup>
import { ref } from 'vue'
import HistoryInfoBlock from './HistoryInfoBlock.vue';

const active = ref(false);

function changeActive(){
    active.value=!active.value;
}

</script>

<template>
    <div class="w-10/12 text-white">
        <div class="flex items-center justify-between border-2 border-neutral-200 rounded-tl-2xl rounded-tr-2xl pl-1 pr-1 mb-2 h-10">
            <div class="text-center text-xl w-1/2" :class="{ 'education-on': !active }" @click="changeActive()">Education</div>
            <div class="text-center text-xl w-1/2" :class="{ 'work-on': active }" @click="changeActive()">Work</div>
        </div>
        <div class="w-full border-2 rounded-b-2xl border-neutral-500">
            <div class="w-full h-full history_pl pt-10 opacity_transition" :class="{ 'inactive_his' : active}">
                <HistoryInfoBlock :name="'Chulalongkorn University'" :time_text="'2024 - now'" :img_path="'/src/assets/logo/chula_logo.png'" :type="'University'"
                    :desc="['Currently studying Computer Science.']"
                />
                <HistoryInfoBlock :name="'Chonradsadornumrung School'" :time_text="'2021 - 2024'" :img_path="'/src/assets/logo/cru_logo.png'" :type="'High School'"
                    :desc="['Enrolled in SMTE program.']"
                />
                <HistoryInfoBlock :name="'Chonradsadornumrung School'" :time_text="'2018 - 2021'" :img_path="'/src/assets/logo/cru_logo.png'" :type="'Middle School'"
                    :desc="['Enrolled in SMTE program.']"
                />
            </div>
            <div class="w-full h-115 grid place-items-center opacity_transition" :class="{ 'inactive_his' : !active}">
                None at the moment.
            </div>
        </div>
        <div class="inactive">

        </div>
    </div>
</template>

<style>
@import "tailwindcss";

.opacity_transition {
    transition: opacity 250ms ease-in-out;
}

.inactive_his {
    opacity: 0;
    display: none;
}

.history_pl {
    @apply pl-10
}

.education-on {
    border-radius: 12px 0px 0px 0px;
    transition: all 300ms ease-in-out;
    @apply bg-white text-neutral-950
}

.work-on {
    border-radius: 0px 12px 0px 0px;
    transition: all 300ms ease-in-out;
    @apply bg-white text-neutral-950
}

@media(max-width: 500px){
    .history_pl {
        @apply pl-5
    }
}
</style>