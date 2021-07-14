<template>
  <div v-if="showSearch" @click.self="closeSearch" class="wrapper search">
    <div class="block-input">
      <p class="text text--light block-input__search">Search</p>
      <input class="input title" type="text" placeholder="Type something" />
      <p class="text block-input__close" @click="closeSearch">Close</p>
    </div>
    <div class="block-search">
      <p class="text text--light">Telecom</p>
      <table-search :items="itemsTelecom" />
    </div>
    <div class="block-search">
      <p class="text text--light">Author</p>
      <table-search :items="itemsAuthor"></table-search>
    </div>
  </div>
</template>

<script>
import TableSearch from "@/components/ModalSearch/TableSearch";
import { SEARCH_TELECOM } from "@/data/SEARCH_TELECOM";
import { SEARCH_AUTHOR } from "@/data/SEARCH_AUTHOR";
export default {
  name: "Search",
  components: { TableSearch },
  data() {
    return {
      itemsTelecom: SEARCH_TELECOM,
      itemsAuthor: SEARCH_AUTHOR,
    };
  },
  props: {
    showSearch: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    closeSearch() {
      this.$emit("closeSearch");
    },
  },
};
</script>

<style lang="scss">
.search {
  z-index: 1;
  position: fixed;
  width: 100vw;
  height: 100vh;
  background: #ffffff;
  overflow-y: auto;
  top: 0;
  display: flex;
  flex-direction: column;
  gap: 48px;
}
.input {
  border: none;
  outline: 0;
  box-shadow: none;
  caret-color: #00ffd1;
  padding: 0;
  width: 100%;
}
.block-input {
  display: grid;
  grid-template-columns: 12.5% 1fr 10%;
  padding-bottom: 52px;
  padding-top: 24px;
  @media (max-width: $screen-laptop) {
    padding-bottom: 20px;
    grid-template-columns: 9.3% 1fr 10%;
    .text {
      font-size: 16px;
    }
  }
  @media (max-width: $screen-square) {
    grid-template-columns: repeat(3, auto);
  }
  @media (max-width: $screen-tablet) {
    &__search {
      grid-area: search;
    }
    &__close {
      grid-area: close;
    }
    .input {
      grid-area: input;
    }
    grid-row-gap: 30px;
    padding-bottom: 0;
    grid-template-rows: auto;
    grid-template-areas:
      "search . close"
      "input input input";
  }
  &__search {
    justify-self: start;
    //margin-top: 8px;
  }
  &__close {
    justify-self: end;
    //margin-top: 8px;
  }
}
.block-search {
  border-top: 0.5px solid #000000;
  display: grid;
  grid-template-columns: 12.5% 1fr;
  @media (max-width: $screen-laptop) {
    grid-template-columns: 9.3% 1fr;
  }
  .text {
    padding: 24px 0;
    @media (max-width: $screen-laptop) {
      font-size: 16px;
    }
    @media (max-width: $screen-mobile) {
      padding-top: 16px;
    }
  }
  @media (max-width: $screen-tablet) {
    display: flex;
    flex-direction: column;
  }
  @media (max-width: $screen-mobile) {
    display: flex;
    flex-direction: column;
  }
}
</style>
