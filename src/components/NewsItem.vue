<template>
  <div class="news-item" v-if="news" :style="`grid-column: span ${news.size}`">
    <p class="news-item__title">{{ news.title }}</p>
    <img :src="news.img" alt="" />
    <div class="news-item__post">
      <p class="text">4 mins ago</p>
      <div class="news-item__author">
        <p class="text">{{ news.author.name }}</p>
        <img :src="news.author.img" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "NewsItem",
  props: {
    news: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.news-item {
  &__title {
    height: 144px;
    border-top: 0.5px solid #000000;
    padding-top: 24px;
    font-family: $font, sans-serif;
    font-size: 28px;
    line-height: 130%;
    color: $font-color-dark;
    @media (max-width: $screen-laptop) {
      font-size: 20px;
      padding-top: 16px;
    }
    @media (max-width: $screen-mobile) {
      font-size: 16px;
    }
  }
  &__post {
    margin-top: 14px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  &__author {
    display: flex;
    align-items: center;
    gap: 8px;
  }
}
</style>
