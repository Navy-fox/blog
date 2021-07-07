<template>
  <div class="preview-title">
    <img src="/icon/icon38.svg" alt="" class="preview-title__img" />
    <p class="title">Wade Warren</p>
    <p class="subtitle">
      They describe a universe consisting of bodies moving with clockwork
      predicatability on a stage of absolute space and time.
    </p>
  </div>
</template>

<script>
export default {
  name: "PreviewTitle",
};
</script>

<style lang="scss">
.preview-title {
  display: grid;
  grid-template-columns: 48px 1fr;
  grid-template-rows: 48px 1fr;
  grid-row-gap: 16px;
  grid-column-gap: 24px;
  align-items: flex-end;
  margin-left: 71px;
  margin-top: 53px;
  margin-bottom: 80px;
  margin-right: 700px;
  @media (max-width: $screen-laptop) {
    margin-top: 32px;
    margin-bottom: 64px;
    margin-right: 350px;
  }
  @media (max-width: $screen-mobile) {
    grid-column-gap: 8px;
    margin: 0 24px 48px;
  }
  .subtitle {
    grid-column: 2 / 3;
    @media (max-width: $screen-mobile) {
      grid-column: 1 / 3;
    }
  }

  &__img {
    width: 48px;
    height: 48px;
    @media (max-width: $screen-laptop) {
      width: 40px;
      height: 40px;
    }
    @media (max-width: $screen-mobile) {
      width: 32px;
      height: 32px;
    }
  }
}
</style>
