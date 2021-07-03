<template>
  <div class="news-line">
    <news-item v-for="(item, key) in news" :key="key" :news="item" />
  </div>
</template>

<script>
import NewsItem from "@/components/NewsItem";
export default {
  name: "NewsLine",
  components: { NewsItem },
  props: {
    news: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style lang="scss">
.news-line {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  grid-column-gap: 32px;
  grid-row-gap: 120px;
}
</style>
