<template>
  <div class="blog-title">
    <router-link to="" class="text only-desktop">Back</router-link>
    <p class="title">
      10GB bundle - the most popular plan, comparison price TTM and competitors
    </p>
    <div class="blog-title__post">
      <p class="text">4 mins ago</p>
      <div class="blog-title__author">
        <img :src="banners.top.author.img" alt="" />
        <p class="text">{{ banners.top.author.name }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import { BANNERS } from "@/data/BANNERS";

export default {
  name: "BlogTitle",
  data() {
    return {
      banners: BANNERS,
    };
  },
};
</script>

<style lang="scss">
.blog-title {
  display: grid;
  grid-template-columns: 37px 1fr;
  grid-column-gap: 80px;
  grid-row-gap: 80px;
  margin: 28px 35% 24px 24px;
  @media (max-width: $screen-laptop) {
    margin-top: 8px;
    margin-right: 25%;
    grid-row-gap: 60px;
  }
  @media (max-width: $screen-square) {
    margin-right: 15%;
  }
  @media (max-width: $screen-tablet) {
    margin-right: 24px;
    grid-column-gap: 32px;
    grid-row-gap: 48px;
  }
  @media (max-width: $screen-mobile) {
    display: flex;
    flex-direction: column;
    gap: 16px;
    margin-top: 10px;
    margin-bottom: 48px;
  }
  &__post {
    grid-column: 2 / 3;
    display: flex;
    gap: 425px;
    align-items: center;
    @media (max-width: $screen-laptop) {
      gap: 240px;
    }
    @media (max-width: $screen-mobile) {
      flex-direction: row-reverse;
      justify-content: space-between;
    }
  }
  &__author {
    display: flex;
    align-items: center;
    gap: 12px;
    @media (max-width: $screen-laptop) {
      gap: 5px;
    }
  }
}
</style>
