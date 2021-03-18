<template>
  <div class="nav__container d-flex flex-column justify-content-center">
    <div class="nav-item__container mx-3 pl-1 py-3">
      <nuxt-link to="/artwork">artwork</nuxt-link>
    </div>
    <div class="nav-item__container mx-3 pl-1 py-3">
      <nuxt-link to="/github-repositories">github repositories</nuxt-link>
    </div>
    <div class="nav-item__container mx-3 pl-1 py-3">
      <nuxt-link to="/digital-products">digital products</nuxt-link>
    </div>
    <div class="nav-item-bottom__container mx-3 pl-1 py-3">
      <nuxt-link to="/digital-products">blog</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.nav__container {
  height: calc(100vh - 80px);
}

.nav-item__container {
  font-size: 7rem;
  border-bottom: 3px solid gray;
}

.nav-item-bottom__container {
  font-size: 7rem;
}
</style>