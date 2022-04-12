<template>
  <footer class="container">
    <section class="footer-left-section">
      <nuxt-link to="/" class="back-to-index">Ronald Rupp</nuxt-link>
      <span>Web Developer based in Vienna, Austria.</span>
    </section>
    <div class="other-links">
      <a href="https://www.linkedin.com/in/ronaldrupp">LinkedIn</a>
      <a href="https://github.com/ronrupp">GitHub</a>
      <a href="mailto:ronald.rupp@outlook.at">E-Mail</a>
    </div>
  </footer>
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
  justify-content: space-between;
  align-items: flex-start;
  color: var(--gray-100);
  @media only screen and (max-width: 768px) {
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
  }
}
.footer-left-section {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
  span {
    margin-top: 0.5em;
    font-size: 0.75rem;
  }
}
.other-links {
  @media only screen and (max-width: 768px) {
    margin-top: 1.5em;
  }
  a {
    color: var(--gray-100);
    font-weight: 600;
    text-decoration: none;
    &:not(:first-child) {
      margin-left: 0.9em;
    }
    transition: 0.3s;
    &:hover {
      filter: brightness(1.5);
    }
  }
}
.back-to-index {
  text-decoration: none;
  position: relative;
  color: var(--gray-100);
  transition: 0.3s;
  font-weight: 600;
  &:hover {
    filter: brightness(1.5);
  }
  /* &::after {
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
  } */
}
</style>
