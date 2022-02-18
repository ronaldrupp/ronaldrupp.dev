<template>
  <div class="container">
    <div class="nav-placeholder"></div>
    <sticky-header title="WAT16">
      <template v-slot:actions>
        <a
          class="website-link"
          href="https://wat16.at"
          target="_blank"
          rel="noreferrer noopener"
          >Website öffnen</a
        >
      </template>
    </sticky-header>
    <main>
      <div class="hero">
        <h1 class="hero-title">WAT16</h1>
        <p class="hero-subtitle">
          Wiener Arbeiter Turn- und Sportverein Ottakring
        </p>
        <img src="~/assets/colin-hadler-home-hero-ui.png" />
      </div>
    </main>
    <tech-details :content="techDetails"> </tech-details>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  head: {
    title: 'WAT16 - Ronald Rupp',
  },
  data() {
    return {
      techDetails: [
        {
          title: 'Frontend',
          description: 'Next.js',
        },
        {
          title: 'CMS',
          description: 'Strapi',
        },
        {
          title: 'Hosting',
          description: 'Custom VPS',
        },
      ],
    }
  },
})
</script>

<style scoped lang="scss">
.hero {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  padding: 5em 0;
  .hero-title {
    font-weight: 800;
    font-size: 2rem;
    text-align: center;
  }
  .hero-subtitle {
    text-align: center;
    font-weight: 300;
    margin: 1.75em 0;
  }
}
img {
  max-width: var(--main-max-width);
  width: 100%;
  padding: 4em 1em;
}
</style>
