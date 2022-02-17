<template>
  <nuxt-link :to="linkTo" class="container"> </nuxt-link>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  props: {
    linkTo: {
      type: String,
      default: '/',
    },
  },
})
</script>

<style scoped>
.container {
  width: 100%;
  height: 400px;
  background-color: rgb(58, 58, 58);
}
</style>
