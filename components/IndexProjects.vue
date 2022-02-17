<template>
  <div class="container">
    <span>Projects</span>
    <div class="projects">
    <project-card linkTo="/projects/colin-hadler" />
    <project-card />
    <project-card />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({})
</script>

<style scoped lang="scss">
.projects {
  display: grid;
  grid-template-columns: repeat(2, minmax(400px, 1fr));
  grid-auto-rows: 400px;
  grid-gap: 1rem;
  width: 100%;
  padding: 0 1em;
}
</style>
