<template>
  <div class="news-card">
    <div class="news-card__image">
      <picture>
        <img :src="data.image" :alt="data.title" width="" height="" />
      </picture>
    </div>

    <div class="news-card__content">
      <div class="news-card__title line-clamp-1">{{ data.title }}</div>
      <p class="news-card__description line-clamp-2">{{ data.description }}</p>

      <a :href="data.url || '#'" class="btn btn-primary btn-sm">Read More</a>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      defailt: () => ({}),
    },
  },
};
</script>

<style>
.news-card {
  --ratio: 1;
  border: 1px solid rgba(255, 255, 255, 0.16);
  background-color: transparent;
  color: inherit;
  text-align: start;
  box-shadow: var(--shadow);
}
.news-card__image {
  aspect-ratio: var(--ratio);
  width: 100%;
  height: auto;
}
.news-card__image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}
.news-card__content {
  padding: 1rem;
}
.news-card__title {
  font-size: 0.875rem;
  font-weight: 500;
  line-height: 1.6;
  max-width: 100%;
  margin-bottom: 0.75rem;
}
.news-card__description {
  font-size: 0.875rem;
  line-height: 1.88;
  font-weight: normal;
  opacity: 0.9;
  margin-bottom: 1rem;
}
</style>
