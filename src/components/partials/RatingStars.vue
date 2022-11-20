<template>
  <div class="rating-stars">
    <span
      v-for="i in maxStars"
      :key="i"
      class="rating-stars__item"
      :class="{ highlight: i <= rating }"
    ></span>
  </div>
</template>

<script>
export default {
  props: {
    rating: {
      type: Number,
      default: () => 0,
    },
  },

  computed: {
    maxStars() {
      return 5;
    },
  },
};
</script>

<style>
.rating-stars {
  display: flex;
  align-content: center;
  justify-content: center;
  gap: 0.35rem;
}
.rating-stars__item {
  color: var(--primary-0);
}
</style>
