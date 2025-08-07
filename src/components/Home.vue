<script setup>
import IconBox from './parts/IconBox.vue';
import ResumeBox from './parts/ResumeBox.vue';
import Background from './parts/Background.vue';
</script>

<template> 
    <div  class="absolute top-1/2 left-1/2 -translate-1/2 flex justify-center items-center gap-8 content-between">
        <img class="profile_pic" src="/cat.jpg">
        <div class= "flex flex-col gap-1.5 text-neutral-100 intro">
            <div class="block">
                <h1 class="ltext font-semibold">RAVINT<br>KOSOL</h1>
                <h1 class="stext text-neutral-300 font-medium italic">Undergraduate</h1>
                <h1 class="vtext mb-2 text-neutral-300 font-medium">➤ Thailand, Bangkok</h1>
            </div>
            <div class="flex flex-col gap-2">
                <ResumeBox />
                <div class="flex gap-3">
                    <IconBox :img_path="'/icon/github_icon.png'" :link="'https://github.com/mxilia'"/>
                    <IconBox :img_path="'/icon/linkedin_logo.png'" :link="''"/>
                    <IconBox :img_path="'/icon/mail_logo.png'" :link="''"/>
                    <IconBox :img_path="'/icon/phone_logo.png'" :link="''"/>
                </div>
            </div>
        </div>
    </div>
    <Background />
</template>

<style lang="css" scoped>
@import "tailwindcss";

.profile_pic {
    @apply object-cover rounded-2xl border-1 border-neutral-400 w-65 h-70
}

.intro {
    @apply h-68
}

.ltext {
    @apply text-6xl
}

.stext {
    @apply text-2xl
}

@media(max-width: 500px){
    .profile_pic {
        @apply object-cover rounded-2xl border-1 border-neutral-400 w-40 h-50
    }

    .intro {
        @apply h-50
    }

    .ltext {
        @apply text-4xl
    }

    .stext {
        @apply text-lg
    }

    .vtext {
        @apply text-xs
    }
}
</style>