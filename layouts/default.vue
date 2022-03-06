<template>
  <div>
    <portal-target name="overlay"> </portal-target>
    <Navigation></Navigation>
    <transition name="page">
      <Nuxt />
    </transition>
    <the-footer />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  transition: 'fade',
})
</script>
