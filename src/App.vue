<template>
  <AppLayout>
    <!--  -->
    <home />
  </AppLayout>
</template>

<script>
import AppLayout from "./layouts/AppLayout.vue";
import Home from "./views/Home/index.vue";

export default {
  components: {
    AppLayout,
    Home,
  },
};
</script>

<style></style>
