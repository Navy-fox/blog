<template>
  <div id="app">
    <MenuMobile :show="show" @closeMenu="closeMenu" />
    <Header class="only-desktop" />
    <HeaderMobile class="only-mobile" @openMenu="openMenu" />
    <router-view />
  </div>
</template>

<script>
import Header from "@/components/Header";
import HeaderMobile from "@/components/HeaderMobile";
import MenuMobile from "@/components/MenuMobile";
export default {
  components: { MenuMobile, Header, HeaderMobile },
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
