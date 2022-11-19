<template>
  <div class="p-home">
    <hero />

    <services />

    <works />

    <about />
  </div>
</template>

<script>
import Hero from "../../components/section/Hero.vue";
import Services from "../../components/section/Services.vue";
import Works from "../../components/section/Works.vue";
import About from "../../components/section/About.vue";

export default {
  components: {
    Hero,
    Services,
    Works,
    About,
  },
};
</script>
