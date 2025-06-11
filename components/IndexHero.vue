<script setup lang="ts">
import { NuxtPicture } from '#components'
</script>

<template>
  <div v-gsap.timeline class="wrapper hero">
    <!-- <div class="block w-full h-[100vh] bg-amber-50" /> -->
    <NuxtPicture
      v-gsap.add.from="{ height: 0, opacity: 0, duration: 1 }"
      src="/images/AnikHero.webp"
    />
    <h1
      v-gsap.add.from="{ x: -320, opacity: 0 }"
      class="text-[7em] hero title text-amber-950"
    >
      Anik von Rohr
    </h1>
  </div>
</template>

<style>
.wrapper {
  width: 100%;
  overflow: hidden;
  position: relative;
}
img {
  width: 100%;
  aspect-ratio: 16 / 9;
  object-fit: cover;
}
.title {
  position: absolute;
  top: 50%;
  left: 15%;
}
</style>
