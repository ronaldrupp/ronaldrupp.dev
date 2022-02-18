<template>
  <NuxtLink
    :to="linkTo"
    class="nav-link client-link overlay"
    @mouseenter.native="playVideo"
    @mouseleave.native="stopVideo"
  >
    <span>{{ title }}</span>
    <div class="shadow"></div>
    <video class="preview-video" muted playsinline loop ref="videoPlayPreview">
      <source :src="`${backgroundVideoSrc}`" type="video/mp4" />
    </video>
    <img :src="`${backgroundImageSrc}`" class="background-img" />
  </NuxtLink>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'No project title set',
    },
    linkTo: {
      type: String,
      default: '#',
    },
    backgroundImageSrc: String,
    backgroundVideoSrc: String,
  },
  methods: {
    playVideo() {
      if (this.$refs.videoPlayPreview) {
        this.$refs.videoPlayPreview.currentTime = 0
        this.$refs.videoPlayPreview.play()
        this.$refs.videoPlayPreview.style.opacity = 1
      }
    },
    stopVideo() {
      if (this.$refs.videoPlayPreview) {
        this.$refs.videoPlayPreview.pause()
        this.$refs.videoPlayPreview.style.opacity = 0
      }
    },
  },
}
</script>

<style lang="scss" scoped>
.nav-link {
  font-size: 2rem;
  color: white;
  text-decoration: none;
  padding: 1rem 0;
  font-weight: 800;
}
.client-link {
  background-color: rgb(54, 54, 54);
  width: 100%;
  padding: 0.5em;
  height: 150px;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  position: relative;
  span {
    z-index: 3;
  }
  .background-img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    position: absolute;
    inset: 0;
    z-index: 0;
  }
  .shadow {
    width: 100%;
    height: 100%;
    position: absolute;
    inset: 0;
    z-index: 2;
    background: linear-gradient(-90deg, transparent, rgba(0, 0, 0, 0.5));
  }
  .preview-video {
    width: 100%;
    height: 100%;
    object-fit: cover;
    position: absolute;
    inset: 0;
    z-index: 1;
    opacity: 0;
    transition: 1s;
  }
}
</style>
