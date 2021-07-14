<template>
  <div id="app">
    <MenuMobile :show="show" @closeMenu="closeMenu" />
    <search :show-search="showSearch" @closeSearch="closeSearch" />
    <Header class="only-desktop" @openSearch="openSearch" />
    <HeaderMobile
      class="only-mobile"
      @openSearch="openSearch"
      @openMenu="openMenu"
      v-if="!show && !showSearch"
    />
    <router-view />
  </div>
</template>

<script>
import Header from "@/components/global/Header";
import HeaderMobile from "@/components/global/HeaderMobile";
import MenuMobile from "@/components/global/MenuMobile";
import Search from "@/components/ModalSearch/Search";

export default {
  components: { Search, MenuMobile, Header, HeaderMobile },
  data() {
    return {
      show: false,
      showSearch: false,
    };
  },
  methods: {
    openMenu() {
      this.show = true;
    },
    closeMenu() {
      this.show = false;
    },
    openSearch() {
      this.showSearch = true;
    },
    closeSearch() {
      this.showSearch = false;
    },
  },
};
</script>

<style lang="scss">
#app {
  max-width: 1920px;
  margin: 0 auto;
}
</style>
