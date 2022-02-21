<template>
  <footer class="container"><nuxt-link to="/" class="back-to-index">Ronald Rupp</nuxt-link></footer>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({})
</script>

<style scoped lang="scss">
.container {
  max-width: var(--main-max-width);
  margin: 0 auto;
  padding: 4em 1em;
  display: flex;
  justify-content: center;
  align-items: center;
}
.back-to-index {
  color: var(--gray-100);
  text-decoration: none;
  position: relative;
  font-weight: 600;
  &::after {
    content: '';
    position: absolute;
    height: 1px;
    background-color: var(--gray-100);
    bottom: 0;
    left: 0;
    width: 100%;
    transform: scaleX(0);
    transition: 0.6s cubic-bezier(0.19, 1, 0.22, 1) 0s,
      -webkit-transform 0.6s cubic-bezier(0.19, 1, 0.22, 1) 0s;
    transform-origin: center center;
  }
  &:hover {
    &::after {
      transform: scaleX(1);
    }
  }
}
</style>
