<template>
  <div class="container">
    <div class="projects">
      <project-card
        linkTo="/projects/colin-hadler"
        title="Colin Hadler"
        :videoSrc="require('~/assets/hero-v0.mp4')"
        description="Jugendbuchautor aus Österreich"
      />
      <project-card
        linkTo="/projects/ahw-display"
        title="AHW Display"
        :videoSrc="require('~/assets/ahw-display-nav-video.mp4')"
        description=" Infoscreen für Klient:innen im Haus der Aids Hilfe Wien."
      />
      <project-card
        linkTo="/projects/wat16"
        title="WAT16"
        :videoSrc="require('~/assets/wat16-highlight.mp4')"
        description="Wiener Arbeiter Turn- und Sportverein Ottakring"
      />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({})
</script>

<style scoped lang="scss">
.projects {
  width: 100%;
}
</style>
