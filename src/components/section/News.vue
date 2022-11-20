<template>
  <section class="section news">
    <div class="container">
      <div class="section__header">
        <h2 class="section__title">Latest News.</h2>
        <span class="section-subtitle">Check out some of our news</span>

        <div class="news__cards">
          <news-card
            v-for="(item, index) in news"
            :key="item.id || index"
            :data="item"
          />
        </div>
      </div>
    </div>

    <div class="section-vertical"></div>
  </section>
</template>

<script lang="js">
import NewsCard from "../partials/NewsCard.vue";

export default {
  components: {
    NewsCard,
  },

  computed: {
    news() {
      return [
        {
          title: "Cloud this VR sketching tool be coming of age for designers in the future?",
          description: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Odit laborum a veritatis. Aspernatur, cumque atque.",
          image: "./news-1.jpg",
          url: "",
        },
        {
          title: "8 Cities That Show You What The Future Will Look Like (Innovative Ideas)",
          description: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Odit laborum a veritatis. Aspernatur, cumque atque.",
          image: "./news-2.jpg",
          url: "",
        },
        {
          title: "15 Gifts Ideas for Mom and Dad. Wherever They Are This Year",
          description: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Odit laborum a veritatis. Aspernatur, cumque atque.",
          image: "./news-3.jpg",
          url: "",
        },
      ]
    }
  },
};
</script>

<style>
.news {
  background-color: var(--dark-1);
  color: var(--light-0);
}

.news__cards {
  margin-top: 2rem;
  --repeat: 1;
  display: grid;
  grid-template-columns: repeat(var(--repeat), minmax(0, 1fr));
  gap: 1rem;
}

@media (min-width: 48em) {
  .news__cards {
    margin-top: 3.5rem;
    --repeat: 3;
  }
  .news .section__header {
    text-align: center;
    flex-direction: column;
    gap: 0;
  }
  .news .section__title:before {
    display: none;
  }
}
@media (min-width: 62em) {
  .news__cards {
    margin-top: 5rem;
  }
}
</style>
