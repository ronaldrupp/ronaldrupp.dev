<template>
  <div class="container">
    <div class="inner-container">
      <div></div>
      <div class="menu-center"><h1>Ronald Rupp</h1></div>
      <div class="menu-right">
        <button @click="toggleDetailedMenu" class="btn-menu">Menu</button>
      </div>
    </div>
    <Transition name="slide">
      <div v-if="isShowing" class="detailed-menu">
        <div class="detailed-menu-inner-container">
          <div class="detailed-menu-header">
            <NuxtLink to="/" class="nav-link">Ronald Rupp</NuxtLink>
            <button @click="toggleDetailedMenu">Close Menu</button>
          </div>
          <div class="clients-container">
            <span>Clients</span>
            <div class="clients">
              <NuxtLink to="/client/colinhadler" class="nav-link client-link">
                <span>Colin Hadler</span>
                <div class="shadow"></div>
                <img src="~/assets/colin-hadler.jpeg" class="background-img" />
              </NuxtLink>
              <NuxtLink to="/client/wat16" class="nav-link client-link">
                <span>WAT16</span>
                <div class="shadow"></div>
                <img src="~/assets/wat16.webp" class="background-img" />
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </Transition>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'Navigation',
  data() {
    return {
      isShowing: false,
    }
  },
  methods: {
    toggleDetailedMenu() {
      if (document.body.style.overflowY == 'hidden')
        document.body.style.overflowY = ''
      else {
        document.body.style.overflowY = 'hidden'
      }
      this.isShowing = !this.isShowing
    },
  },
})
</script>

<style scoped lang="scss">
.container {
  width: 100%;
  padding: 75px 0;
}

.inner-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  width: 100%;
  max-width: var(--main-max-width);
  margin: 0 auto;
  @media only screen and (max-width: 768px){
   padding: 1rem;
  }
}
.menu-center {
  display: grid;
  place-items: center;
  h1{
    font-weight: 600;
    text-align: center;
  }
}
.menu-right {
  display: grid;
  place-items: right;
}
.btn-menu {
  background-color: transparent;
  border: none;
  color: white;
  font-size: 1rem;
  cursor: pointer;
}

.detailed-menu {
  position: fixed;
  inset: 0;
  z-index: 2;
  background-color: var(--main-background-color);
  overflow-y: auto;
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
  padding-top: 75px;
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

.clients-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  width: 100%;
  padding: 1.75em 0;
  span {
    font-size: 2rem;
  }
  @media only screen and (max-width: 768px){
    grid-template-columns: 1fr;
  }
}

.clients {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
}

.client-link {
  background-color: rgb(54, 54, 54);
  width: 100%;
  margin: 0.5em 0;
  padding: 0.5em;
  height: 150px;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  position: relative;
  span {
    z-index: 2;
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
    z-index: 1;
    background: linear-gradient(-90deg, transparent, rgba(0, 0, 0, 0.4));
  }
}
.detailed-menu-header {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid rgb(48, 48, 48);
  padding: 1em 0;
  button {
    border: none;
    background: transparent;
    color: var(--main-font-color);
    font-size: 1rem;
    cursor: pointer;
  }
}
</style>
