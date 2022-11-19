<template>
  <section class="section about">
    <div class="container">
      <h2 class="section__title">About.</h2>
      <p class="section-subtitle">We are more than digital agency</p>

      <div class="about__items">
        <about-card
          v-for="(item, index) in aboutItems"
          :key="item.id || index"
          :data="item"
          :featured="index === 0"
        />
      </div>

      <div class="about__info">
        <div
          v-for="(item, index) in aboutInfo"
          :key="item.id || index"
          class="item"
        >
          <h4 class="item__title font-heading">{{ item.title }}</h4>
          <p class="item__description">{{ item.description }}</p>
        </div>
      </div>
    </div>

    <div class="section-vertical"></div>
  </section>
</template>

<script>
import AboutCard from "../partials/AboutCard.vue";

export default {
  components: {
    AboutCard,
  },

  computed: {
    aboutItems() {
      return [
        {
          title: "Team Work",
          caption: "Committed and creative",
          image: "./team-work.jpg",
        },
        {
          title: "Philosophy",
          caption: "Trust pays off",
          image: "./philosophy.jpg",
        },
        {
          title: "Office",
          caption: "Somewhere on earth",
          image: "./office.jpg",
        },
      ];
    },
    aboutInfo() {
      return [
        {
          title: "Who we are",
          description:
            "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Distinctio nesciunt perferendis consequatur inventore, deserunt consectetur voluptatem accusamus fugit ea iusto.",
        },
        {
          title: "Our philosophy",
          description:
            "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Distinctio nesciunt perferendis consequatur inventore, deserunt consectetur voluptatem accusamus fugit ea iusto.",
        },
        {
          title: "How we work",
          description:
            "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Distinctio nesciunt perferendis consequatur inventore, deserunt consectetur voluptatem accusamus fugit ea iusto.",
        },
      ];
    },
  },
};
</script>

<style>
.about {
  background-color: var(--dark-1);
  color: var(--light-0);
}
.about__items,
.about__info {
  --repeat: 1;
  display: grid;
  grid-template-columns: repeat(var(--repeat), minmax(0, 1fr));
  margin-top: 3rem;
  width: 100%;
  overflow: hidden;
}

.about__items {
  gap: 1rem;
}

.about__info .item {
  padding: 1rem 1.25rem;
  border-inline-end: 3px solid var(--primary-0);
}
.about__info .item:last-child {
  border-inline-end: 0;
}

.about__info .item__title {
  font-size: 1.125rem;
  font-weight: bold;
}
.about__info .item__description {
  font-size: 0.875rem;
  opacity: 0.9;
  line-height: 1.88;
  margin-top: 1rem;
}

@media (min-width: 48em) {
  .about__items,
  .about__info {
    margin-top: 4rem;
  }
  .about__items {
    --repeat: 2;
    align-items: stretch;
    gap: 1.25rem;
  }
  .about__info {
    --repeat: 3;
  }
  .about__info .item__title {
    font-size: 1.25rem;
  }
}
</style>
