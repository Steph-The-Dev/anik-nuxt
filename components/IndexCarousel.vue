<!-- app.vue or pages/index.vue -->
<script setup lang="ts">
// This data is now separate from the component logic
const slides = [
  {
    imageSrc: 'https://assets.codepen.io/2585/Roboto.svg',
    imageAlt:
      'a black and white line drawing of a futuristic person in a jacket pants and helmet striding forward',
    title: 'Cyber Jumper',
    description:
      'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quae, neque.',
    link: '#',
  },
  {
    imageSrc: 'https://assets.codepen.io/2585/Entertainment.svg',
    imageAlt:
      'a black and white drawing of a person with curly hair, wearing a jacket and pants and holding, what looks like a small media player',
    title: 'Jam Strut',
    description:
      'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
    link: '#',
  },
  {
    imageSrc: 'https://assets.codepen.io/2585/Mechanical+Love.svg',
    imageAlt:
      'a black and white drawing of two people standing side by side with their arms around each other and wearing backpacks',
    title: 'Mechanical Love',
    description:
      'Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.',
    link: '#',
    isInitial: true, // This slide will be centered on load
  },
  {
    imageSrc: 'https://assets.codepen.io/2585/Waiting.svg',
    imageAlt: 'a black and white drawing of a person sitting cross-legged',
    title: 'Waiting Patiently',
    description:
      'Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
    link: '#',
  },
  {
    imageSrc: 'https://assets.codepen.io/2585/New+Beginnings.svg',
    imageAlt:
      'a black and white drawing of a person sitting in an armchair reading a book, the chair has wires that are connected to the person.',
    title: 'New Beginnings Are Beautiful',
    description:
      'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo.',
    link: '#',
  },
]
</script>

<template>
  <div>
    <header>
      <h1>Horizontal Cards Carousel (Nuxt Version)</h1>
      <p>Buttons and markers both anchored to the bottom</p>
    </header>

    <main>
      <!-- Use the component and pass the slides data -->
      <BaseCarousel :slides="slides" />
    </main>
  </div>
</template>

<style scoped>
header {
  text-align: center;
  margin-bottom: 2rem;
}
</style>
