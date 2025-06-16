<!-- components/Carousel.vue -->
<script setup lang="ts">
import { NuxtImg } from '#components'

// Define the structure of a single slide object
interface Slide {
  imageSrc: string
  imageAlt: string
  title: string
  description: string
  link: string
  isInitial?: boolean // To mark the slide that should be visible on load
}

// Define the props for the component
defineProps<{
  slides: Slide[]
}>()
</script>

<template>
  <div role="region" aria-label="Card carousel demo">
    <div
      class="carousel carousel--scroll-markers carousel--scroll-buttons carousel--offscreen-inert"
      aria-live="polite"
    >
      <!-- Loop through the slides data passed via props -->
      <div
        v-for="(slide, index) in slides"
        :key="index"
        class="carousel__slide"
        :data-label="`Slide ${index + 1}`"
      >
        <!--
          Bind the 'scroll-start' class if the slide is marked as initial.
          This class is used by the CSS to ensure this slide is the one
          initially scrolled into view.
        -->
        <article class="card" :class="{ 'scroll-start': slide.isInitial }">
          <figure>
            <picture>
              <NuxtImg
                :src="slide.imageSrc"
                :alt="slide.imageAlt"
                height="800"
                width="500"
                loading="lazy"
              />
            </picture>
            <figcaption>
              <h5>{{ slide.title }}</h5>
              <p>{{ slide.description }}</p>
              <a :href="slide.link">Check it out</a>
            </figcaption>
          </figure>
        </article>
      </div>
    </div>
  </div>
</template>

<style scoped>
/*
    The styles are copied directly from the Astro component.
    'scoped' ensures these styles only apply to this component.
    Modern CSS nesting (&) is used here and is supported by default in Nuxt.
  */
.carousel {
  /* Using container query units requires the parent to be a container */
  container-type: inline-size;
  inline-size: 100%;
  list-style-type: none;
  padding: var(--size-3, 1rem);
  scroll-padding: var(--size-3, 1rem);

  display: grid;
  grid-auto-flow: column;
  gap: var(--size-5, 2rem);

  /* Experimental: Not yet supported in most browsers */
  &::scroll-marker-group {
    padding-block: 0;
    block-size: 44px; /* match buttons */
  }

  &::before,
  &::after {
    content: '';
    display: block;
    inline-size: 50cqi;
  }

  .carousel__slide {
    /* Experimental: Not yet supported in most browsers */
    container-type: scroll-state;
    scroll-snap-align: center;
    scroll-snap-stop: always;
  }

  @media (prefers-reduced-motion: no-preference) {
    & {
      scroll-behavior: smooth;
    }

    /* Experimental: Not yet supported in most browsers */
    @container not scroll-state(snapped: inline) {
      figcaption {
        transform: translateY(100%);
      }
    }
  }

  /* Experimental: Not yet supported in most browsers */
  &::scroll-button(right),
  &::scroll-button(left) {
    position-area: var(--_inner-under);
  }
}

.card {
  inline-size: min(var(--size-content-2, 40ch), 90cqi);
  background: var(--surface-2, #333);
  border-radius: var(--radius-3, 0.5rem);
  box-shadow: var(--shadow-2, 0 4px 6px -1px rgb(0 0 0 / 0.1));
  overflow: clip;
  align-content: end;
}

.card > figure {
  display: grid;
  place-items: end stretch;
}

.card > figure > * {
  grid-area: 1 / 1;
}

.card > figure > figcaption {
  max-inline-size: 100%;
  display: grid;
  justify-items: start;
  gap: var(--size-2, 0.5rem);
  transition:
    transform 0.3s var(--ease-3, ease-in-out),
    opacity 0.3s var(--ease-3, ease-in-out);
  background: linear-gradient(to top, #000, 75%, #0000);
  padding-inline: var(--size-5, 2rem);
  padding-block: var(--size-9, 5rem) var(--size-3, 1rem);
}

.card > figure > figcaption:focus-within {
  transform: translateY(0%);
}

.card h5 {
  color: var(--gray-0, #fff);
}

.card p {
  color: var(--gray-4, #aaa);
}

@media (prefers-color-scheme: light) {
  .card {
    background: var(--surface-2, #fff);
    color: var(--text-1, #222);
  }
  .card h5 {
    color: var(--gray-9, #222);
  }
  .card p {
    color: var(--gray-6, #666);
  }
}
</style>
