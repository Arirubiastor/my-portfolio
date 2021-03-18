<template>
  <div class="nav__container d-flex flex-column justify-content-center">
    <div class="nav-item__container mx-4 pl-1 pr-1 py-3">
      <nuxt-link to="/artwork">artwork</nuxt-link>
      <div>
        <img
          src="~assets/icons/next-128px.png"
          alt="A black arrow pointing to the right"
          class="nav-item__icon"
        />
      </div>
    </div>
    <div class="nav-item__container mx-4 pl-1 py-3">
      <nuxt-link to="/github-repositories">repositories</nuxt-link>
      <div>
        <img
          src="~assets/icons/next-128px.png"
          alt="A black arrow pointing to the right"
          class="nav-item__icon"
        />
      </div>
    </div>
    <div class="nav-item__container mx-4 pl-1 py-3">
      <nuxt-link to="/digital-products">projects</nuxt-link>
      <div>
        <img
          src="~assets/icons/next-128px.png"
          alt="A black arrow pointing to the right"
          class="nav-item__icon"
        />
      </div>
    </div>
    <div class="nav-item-bottom__container mx-4 pl-1 py-3">
      <nuxt-link to="/blog">blog</nuxt-link>
      <div>
        <img
          src="~assets/icons/next-128px.png"
          alt="A black arrow pointing to the right"
          class="nav-item__icon"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  
};
</script>

<style lang="scss">
$text-global-color: #343a40; // gray-800

.nav__container {
  height: calc(100vh - 82px);
}

.nav-item__container {
  font-size: 7rem;
  border-bottom: 3px solid $text-global-color;
  font-weight: 500;
  display: flex;
  justify-content: space-between;
}

.nav-item-bottom__container {
  font-size: 7rem;
  color: $text-global-color;
  font-weight: 500;
  display: flex;
  justify-content: space-between;
}

.nav-item__icon {
  width: 5.5rem;
}
</style>