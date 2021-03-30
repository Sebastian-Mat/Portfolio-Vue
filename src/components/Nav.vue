<template>
  <div class="nav">
    <div class="left">
      <a href="">About</a>
      <a href="">Projects</a>
    </div>
    <div class="right">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="25"
        height="25"
        viewBox="0 0 24 24"
        fill="none"
        stroke="black"
        stroke-width="2"
        stroke-linecap="round"
        stroke-linejoin="round"
        class="feather feather-message-circle"
      >
        <path
          d="M21 11.5a8.38 8.38 0 0 1-.9 3.8 8.5 8.5 0 0 1-7.6 4.7 8.38 8.38 0 0 1-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 0 1-.9-3.8 8.5 8.5 0 0 1 4.7-7.6 8.38 8.38 0 0 1 3.8-.9h.5a8.48 8.48 0 0 1 8 8v.5z"
        ></path>
      </svg>
    </div>
  </div>
</template>

<script>

import { Expo, TweenMax } from "gsap";

export default {
  name: "Nav",
  setup() {},
  mounted() {
    TweenMax.staggerFrom(".left a, .right svg", 1, {
        y: 100,
        opacity: 0,
        delay: 3.7,
        ease: Expo.easeInOut,
    }, 0.1)
  }
};
</script>

<style lang="scss" scoped>

.nav{
    padding: 0 80px;
    height: 100px;
    width: 100%;
    background-color: transparent;
    color: black;
    font-family: Monument;
    font-size: 1.5rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: fixed;

    a{
        text-decoration: none;
        color: black;
        margin-right: 30px;
    }
}

</style>
