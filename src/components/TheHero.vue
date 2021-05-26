<template>
  <section class="hero-container">
    <slot></slot>
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
export default {
  name: "the-hero"
};
</script>
