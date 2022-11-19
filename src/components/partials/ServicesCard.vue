<template>
  <div class="services-card stop-propagation">
    <span class="servicecs-card__icon">
      <img :src="data.icon" :alt="data.title" width="40" height="40" />
    </span>

    <h3 class="services-card__title font-heading">{{ data.title }}</h3>
    <p class="services-card__description">{{ data.description }}</p>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      default: () => ({}),
    },
  },
};
</script>

<style>
.services-card {
  background-color: var(--dark-2);
  padding: 1.25rem;
  border-bottom: 4px solid var(--light-0);
  transition: background-color var(--transition-l), color var(--transition-l);
}
.services-card:hover,
.services-card:focus {
  background-color: var(--primary-0);
  color: var(--dark-0);
}
.services-card__icon {
}
.services-card__title {
  font-size: 1rem;
  margin-block: 1rem;
}
.services-card__description {
  margin-top: 0.875rem;
  font-size: 0.875rem;
  font-weight: normal;
  line-height: 1.88;
  opacity: 0.9;
}

@media (min-width: 48em) {
  .services-card__title {
    font-size: 1.25rem;
    margin-block: 1.25rem;
  }
  .services-card {
    padding: 1.5rem;
  }
}
@media (min-width: 62em) {
  .services-card {
    padding: 1.875rem;
  }
}
</style>
