<template>
  <nav :class="classObject">
    <div class="inner-container">
      <NuxtLink to="/" class="back-to-index">Ronald Rupp</NuxtLink>
      <div class="menu-right">
        <button @click="toggleDetailedMenu" class="btn-menu">Menü</button>
      </div>
    </div>
    <Transition name="slide">
      <div v-if="isShowing" class="detailed-menu">
        <div class="detailed-menu-inner-container">
          <div class="detailed-menu-header">
            <NuxtLink to="/" class="nav-link overlay">Ronald Rupp</NuxtLink>
            <button @click="toggleDetailedMenu">Menü schließen</button>
          </div>
          <div class="clients-container">
            <span>Projekte</span>
            <ul class="clients">
              <navigation-project-card
                linkTo="/projects/colin-hadler"
                :backgroundImageSrc="require('~/assets/colin-hadler.jpeg')"
                :backgroundVideoSrc="require('~/assets/hero-v0.mp4')"
                title="Colin Hadler"
              />
              <navigation-project-card
                linkTo="/projects/ahw-display"
                :backgroundImageSrc="require('~/assets/ahw-display-nav.png')"
                :backgroundVideoSrc="
                  require('~/assets/ahw-display-nav-video.mp4')
                "
                title="AHW Display"
              />
              <navigation-project-card
                linkTo="/projects/wat16"
                :backgroundImageSrc="require('~/assets/wat16.webp')"
                :backgroundVideoSrc="require('~/assets/wat16-highlight.mp4')"
                title="WAT16"
              />
            </ul>
          </div>
        </div>
      </div>
    </Transition>
  </nav>
</template>

<script>
import Vue from 'vue'
import NavigationProjectCard from './NavigationProjectCard.vue'

export default Vue.extend({
  components: { NavigationProjectCard },
  name: 'Navigation',
  data() {
    return {
      isShowing: false,
      y: 0,
      isScrollingToTop: false,
    }
  },
  watch: {
    $route() {
      this.isShowing = false
      document.body.style.overflowY = ''
    },
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  computed: {
    classObject() {
      return {
        container: true,
        fixed: this.$route.path === '/',
        // scrolling: this.y >= 75,
        // moveToTop: this.isScrollingToTop,
      }
    },
  },
  methods: {
    toggleDetailedMenu() {
      if (this.isShowing) {
        document.body.style.overflowY = ''
        this.isShowing = false
      } else {
        document.body.style.overflowY = 'hidden'
        this.isShowing = true
      }
    },
    handleScroll() {
      if (this.y < window.scrollY) this.isScrollingToTop = true
      else this.isScrollingToTop = false

      this.y = window.scrollY
    },
    playVideo() {
      this.$refs.videoPlayPreview.currentTime = 0
      this.$refs.videoPlayPreview.play()
      this.$refs.videoPlayPreview.style.opacity = 1
    },
    stopVideo() {
      this.$refs.videoPlayPreview.pause()
      this.$refs.videoPlayPreview.style.opacity = 0
    },
  },
})
</script>

<style scoped lang="scss">
.container {
  width: 100%;
  padding: 1em 0;
  z-index: 999;
  background-color: rgba(0, 0, 0, 0.6);
  backdrop-filter: blur(10px);
  transition: 0.6s cubic-bezier(0.19, 1, 0.22, 1) 0s,
    -webkit-transform 0.6s cubic-bezier(0.19, 1, 0.22, 1) 0s;
}
.fixed {
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
}
.scrolling {
  padding: 1rem 0;
}
.moveToTop {
  transform: translateY(-100%);
}
.back-to-index {
  color: var(--font-color);
  text-decoration: none;
  position: relative;
  font-weight: 600;
  &::after {
    content: '';
    position: absolute;
    height: 1px;
    background-color: white;
    bottom: 0;
    left: 0;
    width: 100%;
    transform: scaleX(0);
    transition: 0.6s cubic-bezier(0.19, 1, 0.22, 1) 0s,
      -webkit-transform 0.6s cubic-bezier(0.19, 1, 0.22, 1) 0s;
    transform-origin: left center;
  }
  &:hover {
    &::after {
      transform: scaleX(1);
    }
  }
}
.nuxt-link-exact-active::after {
  transform: scaleX(1);
}
.inner-container {
  display: flex;
  justify-content: space-between;
  width: 100%;
  max-width: var(--main-max-width);
  margin: 0 auto;
  padding: 0 1rem;
}
.menu-center {
  display: grid;
  place-items: center;
  h1 {
    font-weight: 600;
    text-align: center;
  }
}
.menu-right {
  display: grid;
  place-items: right;
}
.btn-menu {
  padding: 0;
  background-color: transparent;
  border: none;
  color: white;
  font-size: 1rem;
  position: relative;
  cursor: pointer;
  &::after {
    content: '';
    position: absolute;
    height: 1px;
    bottom: 0;
    left: 0;
    width: 100%;
    background-color: white;
    transform: scaleX(0);
    transition: 0.6s cubic-bezier(0.19, 1, 0.22, 1) 0s,
      -webkit-transform 0.6s cubic-bezier(0.19, 1, 0.22, 1) 0s;
    transform-origin: right center;
  }
  &:hover {
    &::after {
      transform: scaleX(1);
    }
  }
}

.detailed-menu {
  position: fixed;
  inset: 0;
  z-index: 9999;
  background-color: var(--main-background-color);
  overflow-y: auto;
  width: 100%;
  height: 100vh;
}

.slide-enter-active,
.slide-leave-active {
  transition: all 0.6s cubic-bezier(0.19, 1, 0.22, 1) 0s;
  opacity: 1;
  transform: scale(1);
}

.slide-enter,
.slide-leave-to {
  opacity: 0;
  transform: scale(1.1);
}

.detailed-menu-inner-container {
  width: 100%;
  max-width: var(--main-max-width);
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
  padding-inline: 1em;
}

.nav-link {
  font-size: 2rem;
  color: white;
  text-decoration: none;
  padding: 1rem 0;
  font-weight: 800;
}
.overlay {
  @media only screen and (max-width: 768px) {
    font-size: 1.25rem;
  }
}
.clients-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.5em;
  width: 100%;
  padding: 1.75em 0;
  span {
    font-size: 2rem;
    @media only screen and (max-width: 768px) {
      font-size: 1.5rem;
    }
  }
  @media only screen and (max-width: 768px) {
    grid-template-columns: 1fr;
  }
}

.clients {
  display: flex;
  gap: 1.5em;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
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
.detailed-menu-header {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid rgb(48, 48, 48);
  button {
    border: none;
    background: transparent;
    color: var(--main-font-color);
    font-size: 1rem;
    cursor: pointer;
  }
}
</style>
