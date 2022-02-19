<template>
  <div class="container" @mouseenter="playVideo" @mouseleave="stopVideo">
    <div class="overlay">
      <div class="inner-overlay">
        <nuxt-link :to="linkTo" class="title">{{ title }}</nuxt-link>
        <p class="paragraph">{{ description }}</p>
      </div>
    </div>
    <video
      class="background-video"
      ref="videoPlayPreview"
      loop
      muted
      playsinline
    >
      <source :src="videoSrc" type="video/mp4" />
    </video>
  </div>
</template>

<script>
export default {
  props: {
    linkTo: {
      type: String,
      default: '/',
    },
    title: String,
    videoSrc: String,
    description: String,
  },
  methods: {
    playVideo() {
      if (this.$refs.videoPlayPreview) {
        this.$refs.videoPlayPreview.currentTime = 0
        this.$refs.videoPlayPreview.play()
      }
    },
    stopVideo() {
      if (this.$refs.videoPlayPreview) {
        this.$refs.videoPlayPreview.pause()
      }
    },
  },
}
</script>

<style scoped lang="scss">
.paragraph {
  font-size: 1.75rem;
  font-weight: 200;
}
.container {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: flex-start;
  align-items: flex-end;
  background-color: rgb(58, 58, 58);
  position: relative;
}
.title {
  text-decoration: none;
  color: white;
  font-weight: 600;
  font-size: 2.5rem;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  &::after {
    content: '';
    width: 50px;
    height: 50px;
    display: inline-block;
    background: url('~/assets/arrow-right.svg') no-repeat center;
    transform: translateX(-100%);
    opacity: 0;
    transition: 0.6s cubic-bezier(0.19, 1, 0.22, 1) 0s,
      -webkit-transform 0.6s cubic-bezier(0.19, 1, 0.22, 1) 0s;
  }
  &:hover,
  &:active {
    &::after {
      transform: translateX(0%);
      opacity: 1;
    }
  }
}
.overlay {
  position: absolute;
  inset: 0;
  z-index: 2;
}
.inner-overlay {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  flex-direction: column;
  max-width: var(--main-max-width);
  margin: 0 auto;
  width: 100%;
  height: 100%;
  padding: 1em;
}
.background-video {
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: brightness(0.5);
}
</style>
