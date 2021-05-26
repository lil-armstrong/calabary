<template>
  <div class="about relative">
    <the-top-navigation-bar></the-top-navigation-bar>
    <the-hero>
      <header class="h-full about-banner">
        <div
          class="flex flex-col justify-center h-full p-6 md:p-10 gap-4  mx-auto text-center isolate"
        >
          <h1
            class="text-white font-semibold text-5xl md:text-[4rem] leading-snug "
          >
            The brains behind our success
          </h1>
          <p class="text-xl text-gray-300">
            Ecommerce the industry standard for design mockups and prototypes.
            By adding a little bit of Latin to a mockup,
          </p>
        </div>
      </header>
    </the-hero>

    <!-- @s about -->
    <section class="flex container mx-auto lg:py-20 py-10 p-10">
      <div class="md:w-1/2">
        <div class="my-4">
          <header class="py-6">
            <h2 class="md:text-[40px] text-3xl font-medium leading-10">
              It’s about helping you say yes
            </h2>
          </header>
          <p>
            Yes to the things that will make yoi life easier, more fulfilled,
            and more fun. The interview outfit. The tripii of a lifetime. The
            new mattress fow
          </p>
        </div>
        <div class="my-4">
          <header class="py-6">
            <h2 class="md:text-[40px] text-3xl leading-10">
              It’s about helping you say yes
            </h2>
          </header>
          <p>
            Yes to the things that will make yoi life easier, more fulfilled,
            and more fun. The interview outfit. The tripii of a lifetime. The
            new mattress fow
          </p>
        </div>
      </div>
      <div class="md:w-1/2"></div>
    </section>
    <!-- @e about -->
  </div>
</template>
<style lang="scss">
.about-banner {
  &::before {
    content: "";
    width: 100%;
    height: 100%;
    left: 0;
    top: 0;
    position: absolute;
    background: #000000bf;
  }
}
</style>
<script>
import TheTopNavigationBar from "@/components/TheTopNavigationBar.vue";
import TheHero from "@/components/TheHero.vue";

export default {
  name: "about-page",
  components: {
    TheTopNavigationBar,
    TheHero
  }
};
</script>
