<template>
  <section class="section services">
    <div class="container">
      <h2 class="section__title font-heading">Services.</h2>
      <span class="section-subtitle">Our services for clients</span>
    </div>

    <div class="container services__items">
      <services-card
        v-for="(item, index) in servicesItems"
        :key="item.id || index"
        :data="item"
      />
    </div>


    <div class="section-vertical"></div>
  </section>
</template>

<script>
import ServicesCard from "../partials/ServicesCard.vue";

export default {
  components: {
    ServicesCard,
  },

  computed: {
    servicesItems() {
      return [
        {
          title: "Digital Strategy",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio ratione aspernatur adipisci expedita harum!",

          icon: "./pie-chart.svg",
        },
        {
          title: "UX Designs",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio ratione aspernatur adipisci expedita harum!",

          icon: "./edit-2.svg",
        },
        {
          title: "UI Designs",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio ratione aspernatur adipisci expedita harum!",

          icon: "./pen-tool.svg",
        },
        {
          title: "Social Media",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio ratione aspernatur adipisci expedita harum!",

          icon: "./globe.svg",
        },
        {
          title: "Design Concept",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio ratione aspernatur adipisci expedita harum!",

          icon: "./bookmark.svg",
        },
        {
          title: "Media Paring",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio ratione aspernatur adipisci expedita harum!",

          icon: "./link.svg",
        },
      ];
    },
  },
};
</script>

<style>
.services {
  background-color: var(--dark-1);
  color: var(--light-0);
}

.services__items {
  --repeat: 1;
  display: grid;
  grid-template-columns: repeat(var(--repeat), minmax(0, 1fr));
  gap: 1rem;
  margin-top: 3rem;
}

@media (min-width: 48em) {
  .services__items {
    --repeat: 2;
    margin-top: 4rem;
  }
}
@media (min-width: 62em) {
  .services__items {
    --repeat: 3;
  }
}
</style>
