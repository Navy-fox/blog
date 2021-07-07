<template>
  <div class="tags" v-if="tags">
    <p class="tags__text tags__text--light">Tags:</p>
    <div class="tags__line">
      <router-link to="" class="tags__text only-desktop">{{
        tags.slice(0, Math.ceil(tags.length / 2)).join(" / ")
      }}</router-link>
      <router-link to="" class="tags__text only-desktop">{{
        tags.slice(Math.ceil(tags.length / 2)).join(" / ")
      }}</router-link>
      <router-link to="" class="tags__text only-mobile">{{
        tags.slice(0, Math.ceil(tags.length / 3)).join(" / ")
      }}</router-link>
      <router-link to="" class="tags__text only-mobile">{{
        tags
          .slice(Math.ceil(tags.length / 3), Math.ceil(tags.length / 1.3))
          .join(" / ")
      }}</router-link>
      <router-link to="" class="tags__text only-mobile">{{
        tags.slice(Math.ceil(tags.length / 1.3)).join(" / ")
      }}</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "Tags",
  props: {
    tags: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.tags {
  display: flex;
  gap: 72px;
  //max-width: 50%;
  margin: 24px;
  padding-top: 24px;
  border-top: 0.5px solid #000000;
  @media (max-width: $screen-laptop) {
    padding-top: 16px;
  }
  @media (max-width: $screen-mobile) {
    flex-direction: column;
    gap: 32px;
  }
  &__line {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }
  &__text {
    font-family: $font, sans-serif;
    font-size: 20px;
    line-height: 130%;
    color: $font-color-dark;
    @media (max-width: $screen-laptop) {
      font-size: 16px;
    }
    &--light {
      color: $font-color-light;
    }
  }
}
</style>
