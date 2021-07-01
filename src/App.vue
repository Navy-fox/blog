<template>
  <div id="app">
    <Header class="only-desktop" />
    <HeaderMobile class="only-mobile" />
    <router-view />
  </div>
</template>

<script>
import Header from "@/components/Header";
import HeaderMobile from "@/components/HeaderMobile";
export default {
  components: { Header, HeaderMobile },
};
</script>

<style lang="scss">
#app {
  max-width: 1920px;
  margin: 0 auto;
}
</style>
