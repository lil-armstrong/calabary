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
          <h3 class="text-center font-semibold">Register using</h3>
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
            type="text"
            name=""
            id=""
            placeholder="Username"
            class="block"
          />
          <input
            type="email"
            name=""
            id=""
            placeholder="Email address"
            class="block"
          />
          <div class="form-field flex items-start gap-x-3">
            <span>
              <svg
                width="20"
                height="20"
                viewBox="0 0 40 33"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M34.1666 12.375H31.6666V9.62498C31.6666 4.31771 26.4331 0 20 0C13.5669 0 8.33336 4.31771 8.33336 9.62498V12.375H5.83336C5.37273 12.375 5 12.6825 5 13.0625V30.25C5 31.7667 6.49492 33 8.33336 33H31.6667C33.5051 33 35 31.7667 35 30.25V13.0625C35 12.6825 34.6273 12.375 34.1666 12.375ZM22.4952 26.7366C22.5212 26.9306 22.4455 27.1254 22.2877 27.2711C22.1298 27.4167 21.9035 27.5 21.6667 27.5H18.3334C18.0966 27.5 17.8703 27.4167 17.7124 27.2711C17.5545 27.1254 17.4788 26.9307 17.5049 26.7366L18.0306 22.8366C17.177 22.3243 16.6667 21.5139 16.6667 20.625C16.6667 19.1084 18.1616 17.875 20.0001 17.875C21.8385 17.875 23.3334 19.1083 23.3334 20.625C23.3334 21.5139 22.8232 22.3243 21.9695 22.8366L22.4952 26.7366ZM26.6666 12.375H13.3334V9.62498C13.3334 6.59233 16.3241 4.125 20 4.125C23.6759 4.125 26.6666 6.59233 26.6666 9.62498V12.375Z"
                  fill="#232243"
                />
              </svg>
            </span>
            <input
              type="password"
              placeholder="Password"
              name=""
              id=""
              class="block"
            />
            <span>
              <svg
                width="20"
                height="20"
                viewBox="0 0 38 38"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M20.4683 7.25061C18.288 7.25061 16.4075 7.45067 14.8138 7.92199C7.62901 9.76908 0 19.3073 0 19.3073C0 19.3073 9.74525 30.7493 17.5324 30.7493C19.7124 30.7493 21.5932 30.5489 23.1866 30.0772C30.3714 28.23 38 18.693 38 18.693C38 18.693 28.2555 7.25061 20.4683 7.25061ZM18.56 27.009C14.3771 27.009 10.9872 23.6187 10.9872 19.4363C10.9872 15.2531 14.3771 11.8632 18.56 11.8632C22.7428 11.8632 26.1331 15.2531 26.1331 19.4363C26.1331 23.6187 22.7428 27.009 18.56 27.009Z"
                  fill="#232243"
                />
                <path
                  d="M18.7635 15.8533C18.8871 16.0837 18.964 16.343 18.964 16.6232C18.964 17.5291 18.2285 18.2637 17.3231 18.2637C16.6106 18.2637 16.0096 17.806 15.7832 17.1716C15.2803 17.7891 14.9664 18.5676 14.9664 19.4263C14.9664 21.4108 16.5753 23.0205 18.5601 23.0205C20.5449 23.0205 22.1538 21.4116 22.1538 19.4263C22.1538 17.5106 20.651 15.9617 18.7635 15.8533Z"
                  fill="#232243"
                />
              </svg>
            </span>
          </div>
          <small class="text-red-400">
            Your password must be at least 6 characters long and must contain
            letters, numbers and special characters. Cannot contain whitespace.
          </small>
          <label for="keep" class="flex gap-x-3">
            <input type="checkbox" name="" id="keep" />
            <span class="text-xs">Receive news from Sneaks via email</span>
          </label>

          <button
            type="submit"
            class="mt-2 bg-yellow-400 p-3 text-white font-medium"
          >
            Log in
          </button>
          <div class="flex gap-x-3 justify-between">
            <span class="text-xs text-left"
              >Already a member?
              <router-link to="/login">Log in</router-link></span
            >
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
