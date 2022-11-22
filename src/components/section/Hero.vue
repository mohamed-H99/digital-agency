<template>
  <section class="hero">
    <div class="container hero__wrapper">
      <span class="section-subtitle">Creative mind, Creative work</span>
      <h1 class="hero__title font-heading">We are digital agency.</h1>

      <a href="#" class="btn btn-primary">Getting started</a>
    </div>

    <div class="container hero__items">
      <hero-card
        v-for="(item, index) in heroItems"
        :key="item.id || index"
        :data="item"
      />
    </div>
  </section>
</template>

<script>
import HeroCard from "../partials/HeroCard.vue";

export default {
  components: {
    HeroCard,
  },

  computed: {
    heroItems() {
      return [
        {
          title: "Future Concept.",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio ratione aspernatur adipisci expedita harum!",
          icon: "./send.svg",
        },
        {
          title: "The Big Ideas.",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio ratione aspernatur adipisci expedita harum!",
          icon: "./git-pull-request.svg",
        },
        {
          title: "Creative Solutions.",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio ratione aspernatur adipisci expedita harum!",
          icon: "./award.svg",
        },
      ];
    },
  },
};
</script>

<style>
.hero {
  background-color: var(--headerBgColor, var(--dark-0));
  color: var(--headerTextColor, var(--light-0));
  position: relative;
}

.hero__wrapper {
  padding-block: 2rem;
  position: relative;
}
.hero__wrapper:after {
  content: "";
  position: absolute;
  top: 50%;
  inset-inline-end: 0;
  height: 100%;
  width: 100%;
  background: url("./hero-bg.png");
  background-position: right center;
  background-size: contain;
  filter: grayscale(1);
  background-repeat: no-repeat;
  pointer-events: none;
  z-index: 0;
}
[dir="rtl"] .hero__wrapper:after {
  background-position: left center;
}
.hero__title {
  font-size: 2.25rem;
  line-height: 1.25;
  max-width: 15ch;
  margin-block: 2rem;
}

.hero__items {
  margin-top: 2rem;
  --repeat: 1;
  display: grid;
  grid-template-columns: repeat(var(--repeat), minmax(0, 1fr));
  gap: 1rem;
  padding-bottom: 2.5rem;
}

@media (min-width: 48em) {
  .hero__items {
    margin-top: 3rem;
    --repeat: 3;
  }
  .hero__wrapper {
    padding-block: 4rem;
  }
  .hero__title {
    font-size: 3rem;
    margin-block: 3rem;
  }
}
@media (min-width: 62em) {
  /* .hero__items {
    --repeat: 3;
  } */
  .hero__title {
    font-size: 4rem;
    /* margin-block: 4rem; */
  }
  .hero__wrapper {
    padding-block: 5rem;
  }
}
</style>
