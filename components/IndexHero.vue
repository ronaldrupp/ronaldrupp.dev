<template>
  <section class="container">
    <h1 class="main-title">
      Portfolio <span class="main-title-thin">Ronald Rupp</span>
    </h1>
    <video class="video" autoplay muted loop playsinline>
      <source src="~/assets/hero-v0.mp4" type="video/mp4" />
    </video>
  </section>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexHero',
})
</script>

<style scoped lang="scss">
.container {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}
.main-title {
  font-weight: 900;
  text-transform: uppercase;
  font-size: 4rem;
  padding: 2.5em 1em;
  text-align: center;
  @media only screen and (max-width: 768px){
    font-size: 3rem;
  }
}
.main-title-thin {
  font-weight: 100;
}
.video {
  width: 100%;
  /* max-width: var(--main-max-width); */
  background-color: rgb(63, 63, 63);
  height: 600px;
  object-fit: cover;
}
</style>
