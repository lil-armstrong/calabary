<template>
  <section class="hero-container">
    <slot></slot>
    <the-search-bar></the-search-bar>
  </section>
</template>
<style>
.hero-container {
  background: #12122cd9;
  height: 538px;
  max-width: 1440px;
  border-radius: 0px;
  margin: 0 auto;
  position: relative;
}
</style>
<script>
import TheSearchBar from '@/components/TheSearchBar'
export default {
  name: 'the-hero',
  components: {
    TheSearchBar
  }
}
</script>
