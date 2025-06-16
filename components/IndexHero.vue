<script setup lang="ts">
import { NuxtPicture } from '#components'
</script>

<template>
  <div v-gsap.timeline class="wrapper">
    <!-- <div class="block w-full h-[100vh] bg-amber-50" /> -->
    <NuxtPicture
      v-gsap.add.from="{ height: 0, opacity: 0, duration: 1 }"
      src="/images/AnikHero.webp"
    />
    <div
      v-gsap.entrance.slide-right
      v-gsap.stagger.add.from="{ x: -320, opacity: 0, delay: 0.5 }"
      class="hero text bg-amber-50 rounded-2xl"
    >
      <h1 class="title text-amber-950">Anik von Rohr</h1>
      <h2 class="subtitle text-amber-800">Systemische Beratung</h2>
    </div>
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

.hero {
  position: absolute;
  top: 50%;
  left: 10%;
  width: 40vw;
  padding: 2vw;
  transform: skewx(-10deg);
  transform-origin: top left;
  .title {
    /* font-family: 'Playfair Display', serif; */
    font-weight: 400;
    font-size: clamp(1.25rem, 5.5vw, 7rem);
    line-height: 0.8;
  }
  .subtitle {
    /* font-family: 'Source Sans Pro', sans-serif; */
    font-weight: 500;
    font-size: clamp(0.75rem, 3.5vw, 5rem);
    text-size-adjust: 100%;
  }
}
</style>
