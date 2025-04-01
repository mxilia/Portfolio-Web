<script setup>
import NavBar from "@/components/NavBar.vue"
import Home from "@/components/Home.vue"
import About from "@/components/About.vue"
import Project from "@/components/Project.vue"
import Contact from "@/components/Contact.vue"
</script>

<template>
  <NavBar />
  <div class="bg-neutral-950">
    <Home />
    <About />
    <Project />
    <Contact />
  </div>
</template>

<style lang="css" scoped>

</style>
