<template>
  <div class="header-mobile">
    <img src="/icon/logo-moon.svg" alt="" />
    <router-link to="" class="text">Search</router-link>
    <img src="/icon/icons8-menu%202.svg" alt="" />
  </div>
</template>

<script>
export default {
  name: "Header-mobile",
};
</script>

<style lang="scss">
.header-mobile {
  padding: 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
