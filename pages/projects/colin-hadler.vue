<template>
  <div class="container">
    <div class="nav-placeholder"></div>
    <sticky-header title="Colin Hadler">
      <template v-slot:actions>
        <a
          class="website-link"
          href="https://colinhadler.at"
          target="_blank"
          rel="noreferrer noopener"
          >Website öffnen</a
        >
      </template>
    </sticky-header>
    <main>
      <div class="hero">
        <h1 class="hero-title">Colin Hadler</h1>
        <p class="hero-subtitle">Jugendbuchautor aus Österreich.</p>
        <img src="~/assets/colin-hadler-home-hero-ui.png" />
      </div>
      <div class="centered-container">
        <img src="~/assets/colinhadler.at_ancora.png" />
      </div>
      <div class="centered-container">
        <img src="~/assets/colinhadler.at_ancora(Surface Pro 7).png" />
      </div>
      <div class="centered-container">
        <img src="~/assets/colinhadler.at_ancora(Surface Pro 7) (1).png" />
      </div>
      <div class="mobile-screenshots">
        <img src="~/assets/colinhadler.at_ancora(iPhone 12 Pro).png" />
        <img src="~/assets/colinhadler.at_ancora(iPhone 12 Pro) (2).png" />
        <img src="~/assets/colinhadler.at_ancora(iPhone 12 Pro) (1).png" />
      </div>
      <div class="centered-container">
        <img src="~/assets/Screenshot 2022-02-16 at 21.21.33.png" />
      </div>
      <tech-details :content="techDetails"> </tech-details>
    </main>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  head: {
    title: 'Colin Hadler - Ronald Rupp',
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
          description: 'Prismic',
        },
        {
          title: 'Hosting',
          description: 'Vercel',
        },
      ],
    }
  },
})
</script>

<style scoped lang="scss">
/* main {
  margin-top: var(--nav-height);
} */
.centered-container{
  max-width: var(--main-max-width);
  margin: 0 auto;
}
.mobile-screenshots {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  max-width: var(--main-max-width);
  margin: 0 auto;
}
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
