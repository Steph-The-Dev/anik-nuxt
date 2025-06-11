<script setup lang="ts">
import { NuxtPicture } from '#components'
</script>

<template>
  <div class="wrapper hero">
    <!-- <div class="block w-full h-[100vh] bg-amber-50" /> -->
    <h1 class="text-[7em] hero title text-amber-950">Anik von Rohr</h1>
    <NuxtPicture src="/images/AnikHero.webp" />
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
