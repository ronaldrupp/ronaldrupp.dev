<template>
  <div>
    <index-hero />
    <index-projects />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
  scrollToTop: true,
  head: {
    title: 'Ronald Rupp',
  },
})
</script>
