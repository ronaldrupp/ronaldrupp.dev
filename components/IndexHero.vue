<template>
  <div class="container">
    <h1 class="main-title">Website Title</h1>
    <video class="video" autoplay muted loop>
      <source src="" type="mp4/video" />
    </video>
  </div>
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
}
.video {
  width: 100%;
  max-width: var(--main-max-width);
  background-color: rgb(63, 63, 63);
}
</style>
