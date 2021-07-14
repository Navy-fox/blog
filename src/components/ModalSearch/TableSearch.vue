<template>
  <div v-if="items">
    <div class="table-search">
      <div class="table-search__row" v-for="(item, key) in items" :key="key">
        <p class="table-search__text table-search__first" v-if="item.text">
          {{ item.text }}
        </p>
        <p
          class="table-search__text table-search__text--light"
          v-if="item.date"
        >
          {{ item.date | formatDate }}
        </p>
        <div
          class="table-search__ellipse only-mobile"
          v-if="item.date && item.name"
        ></div>
        <p
          class="table-search__text table-search__text--light"
          v-if="item.name"
        >
          {{ item.name }}
        </p>
      </div>
    </div>
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
  filters: {
    formatDate(timeStamp) {
      const date = new Date(timeStamp * 1000);
      const arrMonth = [
        "Jan",
        "Feb",
        "Mar",
        "Apr",
        "May",
        "June",
        "July",
        "Aug",
        "Aug",
        "Sept",
        "Oct",
        "Nov",
        "Dec",
      ];
      return `${
        arrMonth[date.getUTCMonth()]
      } ${date.getDate()}, ${date.getHours()}:${date.getMinutes()}`;
    },
  },
};
</script>

<style lang="scss">
.table-search {
  width: 100%;
  &__row {
    display: grid;
    grid-template-columns: 47.6% 20.5% 31.9%;
    border-top: 0.5px solid #000000;
    padding: 24px 0;
    &:first-child {
      border-top: none;
    }
    @media (max-width: $screen-mobile) {
      border-top: none;
      grid-template-columns: repeat(3, auto);
      align-items: center;
      grid-column-gap: 6px;
      grid-row-gap: 8px;
      justify-content: start;
      padding: 12px 0;
      .table-search__first {
        grid-column: 1 / 4;
      }
    }
  }
  &__ellipse {
    width: 4px;
    height: 4px;
    background-color: $font-color-light;
    border-radius: 50%;
  }
  &__text {
    font-family: $font, sans-serif;
    font-size: 28px;
    line-height: 130%;
    color: $font-color-dark;
    @media (max-width: $screen-laptop) {
      font-size: 20px;
    }
    @media (max-width: $screen-mobile) {
      font-size: 16px;
    }
    &--light {
      color: $font-color-light;
    }
  }
}
</style>
