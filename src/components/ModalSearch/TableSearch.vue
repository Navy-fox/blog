<template>
  <div v-if="items">
    <table class="table-search" rules="rows">
      <tr class="table-search__row" v-for="(item, key) in items" :key="key">
        <td class="table-search__text table-search__first-column">
          {{ item.text }}
        </td>
        <td class="table-search__text table-search__text--light">
          {{ item.date }}
        </td>
        <td
          class="
            table-search__text
            table-search__text--light
            table-search__last-column
          "
        >
          {{ item.name }}
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "TableSearch",
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.table-search {
  width: 100%;
  &__first-column {
    width: 47.6%;
  }
  &__last-column {
    width: 31.9%;
  }
  &__text {
    font-family: $font, sans-serif;
    font-size: 28px;
    line-height: 130%;
    color: $font-color-dark;
    padding: 24px 0;
    @media (max-width: $screen-laptop) {
      font-size: 20px;
    }
    &--light {
      color: $font-color-light;
    }
  }
}
</style>
