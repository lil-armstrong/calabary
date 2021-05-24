<template>
<section class="flex flex-col gap-y-3">
  <section class="flex items-center overflow-x-scroll hide-scrollbar overflow-y-hidden flex-nowrap slider-container w-full" ref="slider-container">
    <slot></slot>
  </section>
  <section class="flex gap-x-2 justify-between p-5">
    <button class="btn--sm rounded" @click.stop="slideLeft" type="button" :disabled="slider.isFirst">
      <svg width="25" height="18" viewBox="0 0 39 16" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path
          d="M0.292892 8.70711C-0.0976295 8.31658 -0.0976295 7.68342 0.292892 7.29289L6.65685 0.928932C7.04738 0.538408 7.68054 0.538408 8.07107 0.928932C8.46159 1.31946 8.46159 1.95262 8.07107 2.34315L2.41422 8L8.07107 13.6569C8.46159 14.0474 8.46159 14.6805 8.07107 15.0711C7.68054 15.4616 7.04738 15.4616 6.65685 15.0711L0.292892 8.70711ZM39 9H1V7H39V9Z"
          fill="#30C2FF" />
      </svg>
    </button>
    <button class="btn--sm rounded" @click.stop="slideRight" type="button" :disabled="slider.isLast">
      <svg width="25" height="18" viewBox="0 0 39 16" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path
          d="M38.7071 8.70711C39.0976 8.31658 39.0976 7.68342 38.7071 7.29289L32.3431 0.928932C31.9526 0.538408 31.3195 0.538408 30.9289 0.928932C30.5384 1.31946 30.5384 1.95262 30.9289 2.34315L36.5858 8L30.9289 13.6569C30.5384 14.0474 30.5384 14.6805 30.9289 15.0711C31.3195 15.4616 31.9526 15.4616 32.3431 15.0711L38.7071 8.70711ZM0 9H38V7H0V9Z"
          fill="#30C2FF" />
      </svg>
    </button>
  </section>
</section>
</template>
<style lang="css" scoped>
.slider-container {
  scroll-behavior: smooth;
}
</style>
<script >
export default {
  props: {
    offsetValue: {
      required: false,
      type: Number || String,
      default: 0
    }
  },
  data() {
    return {
      slider: {
        isInit: false,
        container: null,
        offsetValue: 0,
        scrollOffset: 0,
        expectedScrollCount: 0,
        scrollCount: 0,
        offsetDifference: 0,
        isFirst: true,
        isLast: true
      }
    }
  },
  mounted() {
    this.initSlider(this.offsetValue);
    window.addEventListener('resize', () => {
      this.initSlider(this.offsetValue)
    }, true)
  },
  methods: {
    initSlider(offsetValue) {
      this.slider.container =
        this.$refs['slider-container'] ? this.$refs['slider-container'] : null;

      if (this.slider.container) {
        Object.assign(this.slider, {
          offsetValue,
          isFirst: true,
          isLast: false
        })
        this.slider.isInit = true
        this.slider.scrollOffset = 0
        this.slider.scrollCount = 0

        this.slider.expectedScrollCount = Math.floor(
          this.slider.container.scrollWidth /
          (this.slider.container.clientWidth - offsetValue)
        )
        this.slider.offsetDifference =
          this.slider.container.clientWidth - this.slider.offsetValue ?
          this.slider.container.clientWidth - this.slider.offsetValue :
          0
        this.slider.container.scrollLeft = 0

      }
    },
    slideTo(count) {
      if (count >= 0 && count <= this.slider.scrollCount) {
        if (this.slider.scrollOffset < 0) {
          this.slider.container.scrollLeft = 0
          this.slider.isFirst = true;
        } else
        if (this.slider.scrollOffset + this.slider.container.clientWidth >= this.slider.container.scrollWidth) {
          this.slider.container.scrollLeft = this.slider.container.scrollWidth
          this.slider.isLast = true;
        } else {
          this.slider.container.scrollLeft = this.slider.scrollOffset
          this.slider.isFirst = this.slider.scrollCount === 0
          this.slider.isLast = this.slider.scrollCount >= this.slider.expectedScrollCount
        }

      }
    },
    slideRight() {
      if (
        this.slider.isInit &&
        this.slider.scrollCount < this.slider.expectedScrollCount &&
        this.slider.scrollOffset < this.slider.container.scrollWidth
      ) {
        this.slider.scrollCount++
        this.slider.scrollOffset = (this.slider.container.scrollLeft - this.slider.offsetValue) +
          (this.slider.container.clientWidth)
        this.slideTo(this.slider.scrollCount)
      }
    },
    slideLeft() {
      if (
        this.slider.isInit &&
        this.slider.scrollCount > 0 &&
        this.slider.scrollOffset >= 0
      ) {
        this.slider.scrollCount--
        this.slider.scrollOffset = (this.slider.container.scrollLeft + this.slider.offsetValue) -
          (this.slider.container.clientWidth)
        this.slideTo(this.slider.scrollCount)
      }
    }
  }
}
</script>
