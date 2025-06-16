<script setup lang="ts"></script>

<template>
  <div class="background bg-amber-50">
    <div v-gsap.timeline class="wrapper">
      <NuxtImg
        v-gsap.add.from="{ opacity: 0, duration: 1 }"
        src="/images/AnikHero.webp"
      />
      <div
        v-gsap.entrance.slide-right
        v-gsap.stagger.add.from="{ x: -320, opacity: 0, delay: 0.5 }"
        class="hero text"
      >
        <h1 class="title text-amber-950">Anik von Rohr</h1>
        <h2 class="subtitle text-amber-800">Systemische Beratung</h2>
      </div>
    </div>
  </div>
</template>

<style scoped>
.background {
  width: 100vw;
}
.wrapper {
  position: relative;
  width: 100%;
  clip-path: polygon(0% 0%, 100% 0%, 100% 100%, 0% 85%);

  @media screen and (max-width: 480px) {
    clip-path: none;
  }
}

img {
  width: 100%;
  object-fit: cover;
  aspect-ratio: 16 / 9;
}
.hero {
  position: absolute;
  top: 50%;
  left: 10%;
  width: 40vw;
  padding: 2vw;

  .title {
    font-family: 'Playfair Display', serif;
    font-weight: 700;
    font-size: clamp(1.25rem, 5.5vw, 7rem);
    line-height: 0.8;
  }
  .subtitle {
    font-family: 'Source Sans Pro', sans-serif;
    font-weight: 400;
    font-size: clamp(0.75rem, 3.5vw, 5rem);
    text-size-adjust: 100%;
  }
}
</style>
