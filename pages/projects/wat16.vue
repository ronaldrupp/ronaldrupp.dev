<template>
  <div>
    <div class="nav-placeholder"></div>
    <sticky-header title="WAT16">
      <template v-slot:actions>
        <a
          class="website-link"
          href="https://wat16.at"
          target="_blank"
          rel="noreferrer noopener"
          >Website öffnen</a
        >
      </template>
    </sticky-header>
    <tech-details :content="techDetails"> </tech-details>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
   head: {
    title: 'WAT16 - Ronald Rupp',
  },
  data() {
    return {
      techDetails: [
        {
          title: 'Frontend',
          description: 'Next.js',
        },
        {
          title: 'CMS',
          description: 'Strapi',
        },
        {
          title: 'Hosting',
          description: 'Custom VPS',
        },
      ],
    }
  },
})
</script>

<style scoped></style>
