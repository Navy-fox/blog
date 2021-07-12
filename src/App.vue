<template>
  <div id="app">
    <MenuMobile :show="show" @closeMenu="closeMenu" />
    <Header class="only-desktop" />
    <HeaderMobile class="only-mobile" @openMenu="openMenu" />
    <search />
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
    };
  },
  methods: {
    openMenu() {
      this.show = true;
    },
    closeMenu() {
      this.show = false;
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
