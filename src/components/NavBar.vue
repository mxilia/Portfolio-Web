<script setup>
</script>

<template>
    <nav class="fixed top-5 left-1/2 -translate-x-1/2 z-50 flex justify-around items-center text-white bg-gray-950 thin-white-border w-85 h-8.5">
        <a href="#home">
            <div class="line_hover">Home</div>
        </a>
        <a href="#about">
            <div class="line_hover">About</div>
        </a>
        <a href="#project">
            <div class="line_hover">Project</div>
        </a>
        <a href="#contact">
            <div class="line_hover">Contact</div>
        </a>
        
        
        
    </nav>
</template>

<style lang="css" scoped>

.line_hover{
    transition: scale 250ms ease-in-out;
}

.line_hover:hover{
    scale: 1.2
}
</style>