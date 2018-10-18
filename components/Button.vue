<template>
  <button class="button" role="button" @click="smoothScroll">
    <slot></slot>
    <div v-if="splash" class="button__splash"></div>
  </button>
</template>

<script>
export default {
  props: {
    splash: {
      type: String
    }, 
    options: {
      type: Object,
      default() {
        return {
          duration: 1000,
          toTarget: false
        }
      }
    }
  },
  methods: {
    smoothScroll() {
       if (this.options.toTarget) {
          let curTarget = this.options.toTarget;
          let curDuration = this.options.duration;
      
          let thisTarget = document.querySelector(curTarget);
          let targetPosition = thisTarget.getBoundingClientRect().top;
          let startPosition = window.pageYOffset;
          let distance = targetPosition - startPosition;
          let startTime = null;

          function animation(currentTime) {
            if(startTime === null) startTime = currentTime;
            let timeElapsed = currentTime - startTime;
            let run = ease(timeElapsed, startPosition, distance, curDuration);
            window.scrollTo(0, run);
            if(timeElapsed < curDuration) requestAnimationFrame(animation);
          }
          function ease(t, b, c, d) {
            t /= d/2;
            if (t < 1) return c/2*t*t + b;
            t--;
            return -c/2 * (t*(t-2) - 1) + b;
          }
          requestAnimationFrame(animation);
       }
    }

  }
}


</script>

<style lang="scss">
.button {
  display: inline-block;
  text-align: center;
  white-space: nowrap;
  vertical-align: middle;
  user-select: none;
  border: 1px solid transparent;
  padding: 7px 32px;
  font-size: 14px;
  font-weight: bold;
  line-height: 1.5;
  background: none;
  position: relative;
  cursor: pointer;

  &::before,
  &::after {
    content: "";
    display: block;
    position: absolute;
    left: 0;
    right: 0;
    border-left: 2px solid;
    border-right: 2px solid;
    border-color: var(--purple-brown);
    height: 14px;
  }

  &::before {
    border-top: 2px solid;
    top: 0;
  }
  &::after {
    border-bottom: 2px solid;
    bottom: 0;
  }
}

.button__splash {
  position: absolute;
  top: 0;
  left: 0;
  right: -18px;
  bottom: -8px;
  background: url("~assets/images/button_splash.png") left 5px no-repeat;
  background-size: 100% 100%;
  z-index: -1;
  opacity: .7;
  transition: opacity .3s ease-in-out .2s;
}

.button:hover .button__splash {
  opacity: .9;
}
</style>
