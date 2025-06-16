<script setup lang="ts">
// Define a type for our card object for better code safety and autocompletion
interface Card {
  image: string
  text: string
  alt: string // It's a best practice to provide descriptive alt text for accessibility
}

// The data for our cards, defined as an array of objects.
// This could also be passed down as a prop from a parent component.
const cards: Card[] = [
  {
    image: 'images/card1-batman.webp',
    text: 'Sie haben eine lebhafte Familie und keine ruhige Minute? Sie machen sich Sorgen um ihre Kinder?',
    alt: 'Ein Kind in einem Batman-Kostüm, das Familienleben symbolisiert',
  },
  {
    image: 'images/card2-pencil.webp',
    text: 'Neuorientierung beim Beruf oder Ausbildung?',
    alt: 'Buntstifte und ein Spitzer, die berufliche Orientierung darstellen',
  },
  {
    image: 'images/card3-structure.webp',
    text: 'Sie möchten sich besser abgrenzen können? Sie haben einen Konflikt und wissen nicht wie Sie mit diesem umgehen sollen?',
    alt: 'Geometrische Holzblöcke, die Struktur und Abgrenzung symbolisieren',
  },
  {
    image: 'images/card4-graffiti.webp',
    text: 'Sie möchten etwas in Ihrem Leben verändern? Sie geraten immer wieder in ähnliche Muster und würden dies gern ändern?',
    alt: 'Ein farbenfrohes Graffiti an einer Wand, das Veränderung und neue Muster darstellt',
  },
]
</script>

<template>
  <div class="card-grid-container">
    <!-- We loop over the 'cards' array with v-for -->
    <!-- :key is crucial for Vue's performance and is set to a unique value -->
    <article v-for="card in cards" :key="card.image" class="info-card">
      <div class="card-image-wrapper">
        <NuxtPicture :src="card.image" :alt="card.alt" class="card-image" />
      </div>
      <div class="card-content">
        <p>{{ card.text }}</p>
      </div>
    </article>
  </div>
</template>

<style scoped>
/* 
  Scoped styles mean these CSS rules will only apply to this component,
  preventing conflicts with other styles in your project.
*/

.card-grid-container {
  display: grid;
  /* 
    This is the core of the responsive layout.
    - `repeat(auto-fit, ...)`: Creates as many columns as can fit in the available space.
    - `minmax(300px, 1fr)`: Each column will be at least 300px wide, but can grow
      to an equal fraction (1fr) of the available space. This automatically handles
      the number of cards per row based on screen width.
  */
  grid-template-columns: repeat(auto-fit, minmax(min(350px, 100%), 1fr));
  gap: 2rem; /* Space between the cards */
  padding: 2rem;
  max-width: 1440px;
  margin: 6rem auto 0; /* Center the grid container */
}

.info-card {
  border-radius: 16px; /* Modern rounded corners */
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
  overflow: hidden; /* Ensures the image corners are clipped by the border-radius */
  display: flex;
  flex-direction: column;
  transition:
    transform 0.3s ease-in-out,
    box-shadow 0.3s ease-in-out; /* Smooth transition for the hover animation */
}

/* --- Interaction Animation --- */
.info-card:hover {
  /* Lifts the card up and slightly enlarges it */
  transform: translateY(-8px) scale(1.03);
  /* A more pronounced shadow to enhance the "lifted" effect */
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.12);
}

.card-image-wrapper {
  width: 100%;
  height: 250px; /* A fixed height ensures all cards look uniform */
  overflow: hidden;
}

.card-image {
  width: 100%;
  height: 100%;
  /* 
    Ensures the image covers the entire container without being stretched or squashed.
    It will crop the image to fit, which is perfect for this design.
  */
  object-fit: cover;
  transition: transform 0.3s ease-in-out;
  aspect-ratio: 16 / 9;
}

.info-card:hover .card-image {
  /* A subtle zoom effect on the image when hovering the card */
  transform: scale(1.05);
}

.card-content {
  padding: 1.5rem;
  /* This makes the content area grow to fill any remaining space,
     ensuring cards in the same row have the same height even with
     different amounts of text. */
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  text-align: center;
  backdrop-filter: blur(20px);
  background-color: rgba(226, 19, 19, 0.059);
}

.card-content p {
  margin: 0;
  font-size: clamp(1rem, 3.5vw, 1.5rem);
  line-height: 1.6;
  color: #333;
}

/* --- Mobile Responsiveness --- */
@media (max-width: 768px) {
  .card-grid-container {
    /* Reduce padding and gap on smaller screens */
    padding: 1rem;
    gap: 1.5rem;
  }

  .info-card {
    /* Slightly reduce the corner rounding on smaller screens */
    border-radius: 12px;
  }
}
</style>
