<template>
  <div>
    <TheMenu />
  </div>
</template>

<script>
import TheMenu from "~/components/TheMenu.vue";

import Vue from "vue";
import { BootstrapVue, BootstrapVueIcons } from "bootstrap-vue";

Vue.use(BootstrapVue);
Vue.use(BootstrapVueIcons);

export default {
  layout: 'menu',
  components: {
    TheMenu,
  },
  data() {
    return {
    };
  },
  methods: {
  },
};
</script>

<style lang="scss">



</style>