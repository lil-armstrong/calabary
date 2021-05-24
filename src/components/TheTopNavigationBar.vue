<template>
<nav class="flex justify-between items-center container p-4">
  <section class="w-full">
    <div class="flex items-center gap-x-10">
      <div class="flex items-center justify-start flex-grow gap-x-10">
        <the-logo class="p-2 bg-black"></the-logo>
        <!-- desktop nav links @s -->
        <ul class="fixed flex  flex-col gap-6 text-2xl px-6 left-0 w-full bg-white h-full z-10 top-0  lg:static lg:justify-start lg:text-base lg:flex-row items-start justify-center p-4 lg:gap-6 font-body" :class="{'md:flex hidden ': !showMobileMenu}" >
          <li>
            <router-link to="/">Home</router-link>
          </li>
          <li>
            <router-link to="/about">About</router-link>
          </li>
          <li>
            <router-link to="/about">Merchant</router-link>
          </li>
          <li>
            <router-link to="/about">Shops</router-link>
          </li>
        </ul>
        <!-- hamburger toggle @s -->
        <button class="flex lg:hidden flex-col gap-y-2 z-10 ml-auto " :class="{'fixed top-0 right-0 mr-3 mt-8': showMobileMenu}" @click.stop="toggleMobileMenu">
          <span class="w-8 h-1 bg-black block" :class="{'transform rotate-45 ': showMobileMenu}"></span>
          <span class="w-8 h-1 bg-black block" :class="{'transform -rotate-45 -mt-3': showMobileMenu}"></span>
        </button>
        <!-- hamburger toggle @e -->
        <!-- desktop nav links @e -->
      </div>
      <div class="hidden lg:flex gap-x-4 items-center ">
        <!-- desktop @s -->
        <ul class="flex items-center gap-4 font-body">
          <li>
            <button class="rounded font-medium">Register</button>
          </li>
          <li>
            <button class="bg-yellow-400  text-white p-2 px-4 font-semibold rounded border-white">
              Login
            </button>
          </li>
        </ul>
        <!-- desktop @e -->
      </div>
    </div>
  </section>
</nav>
</template>
<script>
import TheLogo from '@/components/TheLogo.vue'
export default {
  name: 'top-navigation-bar',
  components: {
    TheLogo
  },
  data() {
    return {
      showMobileMenu: false
    }
  },
  methods:{
    toggleMobileMenu(){
      this.showMobileMenu = !this.showMobileMenu
    }
  }
}
</script>
