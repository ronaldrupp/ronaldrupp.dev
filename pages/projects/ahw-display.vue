<template>
  <div class="container">
    <div class="nav-placeholder"></div>
    <sticky-header title="AHW Display">
      <template v-slot:actions>
        <a class="website-link internal-app">Interne App</a>
      </template>
    </sticky-header>

    <main class="main-container">
      <div class="hero">
        <h1 class="hero-title">AHW Display</h1>
        <p class="hero-subtitle">
          Infoscreen für Klient:innen im Haus der Aids Hilfe Wien.
        </p>
        <video
          src="~/assets/ahw-display-hero.mp4"
          class="hero-img"
          muted
          loop
          autoplay
          playsinline
        />
      </div>
      <img src="~/assets/ahw-display-openning-hours-ui.png" />
      <img src="~/assets/ahw-display-video-content-ui.png" />
      <img src="~/assets/ahw-display-fullscreen-overlay-ui.png" />
    </main>
    <tech-details :content="techDetails"> </tech-details>
  </div>
</template>

<script>
export default {
  scrollToTop: true,
   head: {
    title: 'AHW Display - Ronald Rupp',
  },
  data() {
    return {
      techDetails: [
        {
          title: 'Frontend',
          description: 'Create React App',
        },
        {
          title: 'BaaS',
          description: 'Firebase',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.fullscreen-section {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  img {
    width: 100%;
  }
}
.main-container {
  background-color: #fff5da;
  color: black;
}
.nav-placeholder {
  height: 50px;
}
.hero {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  padding: 5em 1em;
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
.hero-img {
  width: 100%;
  max-width: var(--main-max-width);
  margin: 5em auto;
  padding: 0 1em;
}
</style>
