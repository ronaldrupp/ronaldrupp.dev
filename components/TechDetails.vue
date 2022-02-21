<template>
  <div class="container">
    <h5 class="title">Technische Details</h5>
    <ul class="list">
      <li class="row" v-for="(tech, idx) in content" :key="idx">
        <h6>{{ tech.title }}</h6>
        <p>{{ tech.description }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    content: Array,
  },
}
</script>

<style lang="scss" scoped>
.title {
  font-size: 1.75rem;
  font-weight: 600;
  margin: 1em 0;
}
.container {
  width: 100%;
  max-width: var(--main-max-width);
  padding: 2em 1em;
  margin: 0 auto;
}
.row {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  padding: 2em 0;
  border-top: 1px solid rgb(139, 139, 139);

  h6 {
    font-weight: 600;
    font-size: 1.5rem;
  }
  /* &:not(:first-child):not(:last-child) {
    border-bottom: 1px solid rgb(139, 139, 139);
  } */
}
</style>
