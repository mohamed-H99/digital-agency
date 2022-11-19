<template>
  <div class="app-layout">
    <app-header />

    <slot></slot>

    <app-footer />

    <side-menu />
  </div>
</template>

<script>
import AppHeader from "../components/common/AppHeader.vue";
import AppFooter from "../components/common/AppFooter.vue";
import SideMenu from "../components/common/SideMenu.vue";

export default {
  components: {
    AppHeader,
    AppFooter,
    SideMenu,
  },
};
</script>
