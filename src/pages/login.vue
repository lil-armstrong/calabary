<template>
  <div class="min-h-screen bg-black bg-opacity-75 ">
    <div class="lg:w-4/12 lg:p-10 p-4 py-10 flex flex-col items-center mx-auto">
      <div>
        <the-logo></the-logo>
      </div>
      <div class="my-4">
        <p class="text-center text-white text-opacity-50">
          Registering to this website, you accept our Terms & Conditions and our
          Privacy Policy
        </p>
      </div>
      <div class="bg-white flex-grow w-full p-8">
        <div class="flex flex-col gap-y-3 my-4">
          <h3 class="text-center font-semibold">Log in using</h3>
          <ul class="flex items-center justify-center py-2 gap-x-3">
            <li>Facebook</li>
            <li>Google</li>
            <li>Twitter</li>
          </ul>
          <div class="text-xs or-text flex items-center gap-x-2 justify-center">
            Or
          </div>
        </div>
        <form class="flex flex-col gap-y-8 my-2">
          <input
            type="email"
            name=""
            id=""
            placeholder="Email address"
            class="block"
          />
          <input
            type="password"
            placeholder="Password"
            name=""
            id=""
            class="block"
          />
          <label for="keep" class="flex gap-x-3">
            <input type="checkbox" name="" id="keep" />
            <span class="text-xs">Keep me signed in</span>
          </label>

          <button
            type="submit"
            class="mt-2 bg-yellow-400 p-3 text-white font-medium"
          >
            Log in
          </button>
          <div class="flex gap-x-3 justify-between">
            <span class="text-xs text-left"
              >Not a member?
              <router-link to="/register">Register</router-link></span
            >
            <span class="text-xs text-right">Forgot Password</span>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import TheLogo from "@/components/TheLogo.vue";

export default {
  components: {
    TheLogo
  }
};
</script>

<style lang="scss" scoped>
.or-text {
  &:after {
    content: "";
    border: 1px solid #ededed;
    flex-grow: 1;
  }
  &:before {
    content: "";
    border: 1px #ededed solid;
    flex-grow: 1;
  }
}
</style>
