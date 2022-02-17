<template>
  <div class="container">
    <p>
      Lorem Ipsum is simply dummy text of the printing and typesetting industry.
      Lorem Ipsum has been the industry's standard dummy text ever since the
      1500s, when an unknown printer took a galley of type and scrambled it to
      make a type specimen book. It has survived not only five centuries, but
      also the leap into electronic typesetting, remaining essentially
      unchanged.
    </p>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({})
</script>

<style scoped>
.container{
    padding: 50vh 0;
}
p {
  max-width: 55ch;
  margin: 0 auto;
  text-align: center;
  font-size: 1.5rem;
  font-weight: 100;
}
</style>
