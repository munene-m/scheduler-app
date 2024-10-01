<script setup>
import { ref } from 'vue'
import MenuIcon from './icons/MenuIcon.vue'
import MenuClose from './icons/MenuClose.vue'
import GoogleIcon from './icons/GoogleIcon.vue'
import { RouterLink } from 'vue-router'
import CustomButton from './CustomButton.vue'

const showMenu = ref(false)

function toggleMenuIcon() {
  showMenu.value = !showMenu.value
}
</script>
<template>
  <nav class="flex items-center justify-between py-3 px-2 text-light">
    <div class="flex items-center gap-6">
      <img src="" class="w-14 bg-white rounded-full" alt="" />
      <div class="hidden md:flex">
        <ul class="flex items-center justify-center gap-x-5">
          <RouterLink to="/" aria-current="page">Home</RouterLink>

          <RouterLink to="/about">About</RouterLink>
        </ul>
      </div>
    </div>

    <div class="md:flex hidden">
      <custom-button class="bg-primary rounded text-white flex items-center gap-2"
        >Sign in with Google<google-icon
      /></custom-button>
    </div>
    <menu-icon class="md:hidden flex" @click="toggleMenuIcon" v-if="!showMenu" />
    <menu-close v-if="showMenu" @click="toggleMenuIcon" class="md:hidden flex" />
  </nav>
  <div
    v-if="showMenu"
    class="bg-white w-fit px-6 py-2 rounded-md shadow-md absolute z-50 right-2 mt-2 md:hidden"
  >
    <ul class="flex flex-col items-center justify-center gap-y-3">
      <RouterLink to="/" aria-current="page">Home</RouterLink>

      <RouterLink to="/about">About</RouterLink>
      <!-- <RouterLink to="/contact">Contact</RouterLink>
      <RouterLink to="/projects">Projects</RouterLink> -->

      <custom-button class="bg-primary text-white rounded flex items-center gap-2"
        >Sign in with Google<google-icon
      /></custom-button>
    </ul>
  </div>
</template>

<style scoped>
ul li {
  cursor: pointer;
}
.router-link-exact-active {
  color: #37cdbe;
  position: relative;
  text-decoration: none;
}
.router-link-exact-active::before {
  content: '';
  position: absolute;
  width: 100%;
  transform: scaleX(0);
  height: 1px;
  bottom: -2px;
  left: 0;
  background-color: #fff;
  transform-origin: bottom left;
  transition: transform 0.4s ease-out;
}
.router-link-exact-active:hover::before {
  transform: scaleX(1);
}
</style>
