<template>
  <div
    class="banner"
    :style="`height: ${height}px; background-image: url(${img})`"
  >
    <div class="banner__post">
      <p class="text text--white">4 mins ago</p>
      <div class="banner__author">
        <img src="/icon/icon30.svg" alt="" />
        <p class="text text--white">Brooklyn Simmons</p>
      </div>
    </div>
    <p class="banner-title">Helping a local business reinvent itself</p>
  </div>
</template>

<script>
export default {
  name: "Banner",
  props: {
    img: {
      type: String,
      default: "/img/banner-car.svg",
    },
  },
  data() {
    return {
      height: window.innerWidth / 2.14,
    };
  },
  methods: {
    resizeHeight() {
      this.height = window.innerWidth / 2.14;
    },
  },
  created() {
    window.addEventListener("resize", this.resizeHeight);
  },
};
</script>

<style lang="scss">
.banner {
  padding: 24px 142px;
  width: 100%;
  //background-image: url("/img/banner-car.svg");
  background-position: 0 0;
  background-repeat: no-repeat;
  background-size: cover;
  display: grid;
  grid-template-rows: 24px 1fr;
  gap: 32px;
  &__post {
    display: flex;
    align-items: center;
    gap: 115px;
  }
  &__author {
    display: flex;
    align-items: center;
    gap: 12px;
  }
  @media (max-width: $screen-laptop) {
    padding: 16px 142px;
    gap: 24px;
  }
  @media (max-width: $screen-square) {
    padding: 16px 72px;
  }
  @media (max-width: $screen-tablet) {
    padding: 16px 36px;
  }
  @media (max-width: $screen-mobile) {
    padding: 8px 24px;
    gap: 8px;
    &__post {
      justify-content: space-between;
    }
    &__author {
      flex-direction: row-reverse;
    }
  }
}
</style>
