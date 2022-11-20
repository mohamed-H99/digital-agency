<template>
  <div class="p-home">
    <hero />

    <services />

    <works />

    <about />

    <testimonials />
  </div>
</template>

<script>
import Hero from "../../components/section/Hero.vue";
import Services from "../../components/section/Services.vue";
import Works from "../../components/section/Works.vue";
import About from "../../components/section/About.vue";
import Testimonials from "../../components/section/Testimonials.vue";

export default {
  components: {
    Hero,
    Services,
    Works,
    About,
    Testimonials,
  },
};
</script>
