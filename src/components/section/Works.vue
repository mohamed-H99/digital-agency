<template>
  <section class="section works">
    <div class="container">
      <div class="section__header">
        <div>
          <h2 class="section__title font-heading">Works.</h2>
          <span class="section-subtitle">Things we've made</span>
        </div>

        <a href="#" class="btn btn-primary">View All</a>
      </div>
    </div>

    <works-items :items="worksItems" />

    <div class="section-vertical"></div>
  </section>
</template>

<script>
import WorksItems from "../partials/WorksItems.vue";

export default {
  components: {
    WorksItems,
  },

  computed: {
    worksItems() {
      return [
        {
          name: "Work 1",
          image: "./works-1.jpg",
        },
        {
          name: "Work 2",
          image: "./works-2.jpg",
        },
        {
          name: "Work 3",
          image: "./works-3.jpg",
        },
        {
          name: "Work 4",
          image: "./works-4.jpg",
        },
        {
          name: "Work 5",
          image: "./works-5.jpg",
        },
        {
          name: "Work 6",
          image: "./works-6.jpg",
        },
        {
          name: "Work 7",
          image: "./works-7.jpg",
        },
      ];
    },
  },
};
</script>

<style>
.works {
  background-color: var(--dark-2);
  color: var(--light-0);
}
</style>
