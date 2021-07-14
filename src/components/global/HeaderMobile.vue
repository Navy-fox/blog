<template>
  <div class="header-mobile">
    <img src="/icon/logo-moon.svg" alt="" />
    <p class="text" @click="$emit('openSearch')">Search</p>
    <img src="/icon/icons8-menu%202.svg" alt="" @click="$emit('openMenu')" />
  </div>
</template>

<script>
export default {
  name: "Header-mobile",
};
</script>

<style lang="scss">
.header-mobile {
  position: sticky;
  top: 0;
  background: #ffffff;
  padding: 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
