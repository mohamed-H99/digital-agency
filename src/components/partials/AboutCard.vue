<template>
  <div class="about-card" :class="{ featured }">
    <div class="about-card__image">
      <picture>
        <img :src="data.image" :alt="data.title" width="" height="" />
      </picture>
    </div>

    <div class="about-card__content">
      <h4 class="title">{{ data.title }}</h4>
      <caption class="sub">
        {{
          data.caption
        }}
      </caption>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      default: () => ({}),
    },
    featured: Boolean,
  },
};
</script>

<style>
.about-card {
  --ratio: 1.5/1;
  position: relative;
  aspect-ratio: var(--ratio);
  overflow: hidden;
}

.about-card__image {
  width: 100%;
  height: auto;
  pointer-events: none;
}
.about-card__image img {
  width: 100%;
  height: 100%;
  display: block;
  object-fit: cover;
}
.about-card__content {
  position: absolute;
  inset: 0;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  align-items: flex-start;
  padding: 2rem 1.5rem;
  background-color: rgba(0, 0, 0, 0.6);
  color: var(--light-0);
  z-index: 1;
}
.about-card__content .title {
  font-weight: bold;
  font-size: 1rem;
  margin-bottom: 0.75rem;
}
.about-card__content .sub {
  font-size: 0.875rem;
  font-weight: normal;
}

@media (min-width: 48em) {
  .about-card.featured {
    --ratio: unset;
    grid-row-start: 1;
    grid-row-end: 3;
  }
}
</style>
