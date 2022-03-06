<template>
  <div class="container">
    <div class="inner-container">
      <h1 @click="scrollToTop">{{ title }}</h1>
      <div>
        <slot name="actions"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'No title set',
    },
  },
  methods: {
    scrollToTop() {
      window.scrollTo(0, 0)
    },
  },
}
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  height: 50px;
  background-color: rgba(0, 0, 0, 0.6);
  backdrop-filter: saturate(180%) blur(20px);
  transition: 0.6s cubic-bezier(0.19, 1, 0.22, 1) 0s,
    -webkit-transform 0.6s cubic-bezier(0.19, 1, 0.22, 1) 0s;
  h1 {
    font-weight: 600;
    cursor: pointer;
  }
  .inner-container {
    max-width: var(--main-max-width);
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1em;
    margin: 0 auto;
    color: white;
  }
}
</style>
