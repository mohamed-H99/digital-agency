<template>
  <div class="p-home">
    <hero />

    <services />

    <works />

    <about />

    <testimonials />

    <news />

    <contact-us />
  </div>
</template>

<script>
import Hero from "../../components/section/Hero.vue";
import Services from "../../components/section/Services.vue";
import Works from "../../components/section/Works.vue";
import About from "../../components/section/About.vue";
import Testimonials from "../../components/section/Testimonials.vue";
import News from "../../components/section/News.vue";
import ContactUs from "../../components/section/ContactUs.vue";

export default {
  components: {
    Hero,
    Services,
    Works,
    About,
    Testimonials,
    News,
    ContactUs,
  },
};
</script>
