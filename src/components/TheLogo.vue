<template>
  <router-link to="/" class="block">
    <img
      :class="['logo', size]"
      src="../assets/image/logo.svg"
      alt="calabary logo"
    />
  </router-link>
</template>
<script>
export default {
  name: 'TheLogo',
  props: {
    size: {
      default: () => 'base',
      type: String,
      validator: (data) => ['xs', 'sm', 'base', 'lg', 'xl'].includes(data)
    }
  }
}
</script>

<style >
.logo {
  animation: 1s appear;
  transition: all 0.25s ease-in-out;
  width: 100%;
}
.logo.xl {
  max-width: 240px;
}
.logo.lg {
  max-width: 180px;
}
.logo.base {
  max-width: 150px;
}
.logo.sm {
  max-width: 60px;
}
.logo.xs {
  max-width: 30px;
}

@keyframes appear {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>
