<template>
  <div class="header">
    <div class="header__menu header__left-menu">
      <p class="text text--light">To The Moon</p>
      <img src="/icon/logo-moon.svg" alt="" />
      <div id="nav">
        <router-link to="" class="text text--light">All</router-link>
        <router-link to="" class="text">Telecom</router-link>
        <router-link to="" class="text">Finance</router-link>
      </div>
    </div>
    <div class="header__menu header__right-menu">
      <p class="text" @click="$emit('openSearch')">Search</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style lang="scss">
#nav {
  display: flex;
  gap: 24px;
}
.header {
  position: sticky;
  top: 0;
  background: #ffffff;
  display: flex;
  justify-content: space-between;
  padding: 24px;
  &__menu {
    display: flex;
    align-items: center;
    gap: 24px;
  }
}
</style>
