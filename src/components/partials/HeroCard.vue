<template>
  <div class="hero-card stop-propagation">
    <span class="hero-card__icon">
      <img :src="data.icon" :alt="data.title" width="30" height="30" />
    </span>

    <h3 class="hero-card__title font-heading">{{ data.title }}</h3>
    <p class="hero-card__description">{{ data.description }}</p>
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
.hero-card {
  padding: 1.375rem 1rem;
  border: 2px solid transparent;
  transition: border-color var(--transition), transform var(--transition);
  position: relative;
  background-color: var(--dark-2);
}
.hero-card:after {
  height: 1rem;
  content: "";
  position: absolute;
  top: 100%;
  left: 50%;
  transform: translateX(-50%);
  width: 2px;
  background-color: var(--primary-0);
  opacity: 0;
  transition: opacity var(--transition);
}
.hero-card:hover {
  border-color: var(--primary-0);
}
.hero-card:hover:after {
  opacity: 1;
}
.hero-card:active {
  transform: scale(0.95);
}
.hero-card__title {
  font-size: 1.125rem;
  margin-top: 2rem;
}
.hero-card__title:after {
  content: "";
  width: 3rem;
  height: 2px;
  background-color: var(--primary-0);
  display: block;
  margin-top: 0.85rem;
}
.hero-card__description {
  margin-top: 0.875rem;
  font-size: 0.875rem;
  font-weight: normal;
  line-height: 1.88;
  opacity: 0.9;
}

@media (min-width: 48em) {
  .hero-card {
    padding: 2rem 1.375rem;
  }
  .hero-card:after {
    height: 2rem;
  }
}
</style>
