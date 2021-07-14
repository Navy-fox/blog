<template>
  <div v-if="show" @click.self="closeMenu" class="mobile-menu">
    <div class="mobile-menu__shadow"></div>
    <div class="mobile-menu__head">
      <img src="/icon/logo-moon-white.svg" alt="" />
      <button @click="closeMenu">
        <img src="/icon/icons8-menu%203.svg" alt="" />
      </button>
    </div>
    <div class="mobile-menu__body">
      <nav class="mobile-menu__block">
        <a href="" class="mobile-menu__item mobile-menu__item--white">
          Telecom
        </a>
        <a href="" class="mobile-menu__item">Bundles</a>
        <a href="" class="mobile-menu__item">Keep your number</a>
        <a href="" class="mobile-menu__item">Roaming</a>
        <a href="" class="mobile-menu__item">Coverage map</a>
        <a href="" class="mobile-menu__item">Top up</a>
      </nav>
      <nav class="mobile-menu__block">
        <a href="" class="mobile-menu__item mobile-menu__item--white">
          Finance
        </a>
        <a href="" class="mobile-menu__item">Cards</a>
        <a href="" class="mobile-menu__item">Accounts</a>
        <a href="" class="mobile-menu__item">Services</a>
        <a href="" class="mobile-menu__item">Pricing</a>
      </nav>
      <nav class="mobile-menu__block">
        <a href="" class="mobile-menu__item mobile-menu__item--white">
          About Us
        </a>
        <a href="" class="mobile-menu__item mobile-menu__item--white"> Help </a>
        <a href="" class="mobile-menu__item mobile-menu__item--white">
          Refer a Friend
        </a>
        <a href="" class="mobile-menu__item mobile-menu__item--white"> Blog </a>
      </nav>
    </div>
  </div>
</template>

<script>
export default {
  name: "MobileMenu",
  props: {
    show: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    closeMenu() {
      this.$emit("closeMenu");
    },
  },
};
</script>

<style lang="scss">
.mobile-menu {
  position: fixed;
  width: 100vw;
  height: 100vh;
  overflow-y: auto;
  top: 0;
  background: #0f1011;
  &__shadow {
    position: fixed;
    bottom: 0;
    background: linear-gradient(
      360deg,
      #0f1011 34.33%,
      rgba(15, 16, 17, 0) 175%
    );
    z-index: 100;
    height: 22%;
    width: 100vw;
  }
  &__head {
    position: sticky;
    top: 0;
    background: #0f1011;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 20px;
  }
  &__body {
    display: flex;
    flex-direction: column;
    gap: 32px;
    padding-top: 25px;
    padding-left: 22px;
    padding-bottom: calc(48px + 22%);
  }
  &__block {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }
  &__item {
    font-family: $font, sans-serif;
    color: $font-color-light;
    font-size: 24px;
    &--white {
      color: $font-color-white;
    }
  }
}
</style>
