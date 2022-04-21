<template>
  <nav class="app-header">
    <nuxt-link to="/">
      <img
        src="https://www.springfinancial.ca/_nuxt/img/logo.c4b3aa6.svg"
        alt=""
        class="app-header__logo"
      />
    </nuxt-link>
  </nav>
</template>

<script>
export default {
  name: 'AppHeader',
}
</script>

<style scoped lang="scss">
.app-header {
  @apply h-[80px] flex justify-between mx-auto py-[15px];
  .logo {
    @apply max-h-[50px];
  }
}
</style>
