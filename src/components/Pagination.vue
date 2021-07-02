<template>
  <div class="pagination">
    <div
      class="pagination__item"
      :class="page === 1 ? 'pagination__item--active' : ''"
      :key="page"
      v-for="page in pages"
    >
      {{ page }}
    </div>
  </div>
</template>

<script>
export default {
  name: "Pagination",
  data() {
    return {
      pages: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12],
    };
  },
};
</script>

<style lang="scss">
.pagination {
  display: flex;
  align-items: center;
  margin: 120px 24px 72px 24px;
  padding-top: 32px;
  gap: 32px;
  border-top: 0.5px solid #000000;
  @media (max-width: $screen-laptop) {
    gap: 24px;
  }
  @media (max-width: $screen-mobile) {
    gap: 16px;
  }
  &__item {
    font-family: $font, sans-serif;
    font-size: 48px;
    line-height: 100%;
    letter-spacing: 0.01em;
    color: $font-color-dark;
    @media (max-width: $screen-laptop) {
      font-size: 40px;
      letter-spacing: normal;
    }
    @media (max-width: $screen-mobile) {
      font-size: 32px;
      letter-spacing: -0.01em;
    }
    &--active {
      font-family: $font, sans-serif;
      font-size: 48px;
      line-height: 120%;
      color: $font-color-light;
      @media (max-width: $screen-laptop) {
        font-size: 40px;
      }
      @media (max-width: $screen-mobile) {
        font-size: 24px;
        line-height: 130%;
      }
    }
  }
}
</style>
