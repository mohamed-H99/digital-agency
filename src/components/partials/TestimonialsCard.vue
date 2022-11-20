<template>
  <div class="testimonials-card">
    <div class="testimonials-card__box">
      <span class="testimonials-card__icon">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          viewBox="0 0 450 366"
          width="30"
          height="30"
        >
          <title>Left double quotation mark</title>
          <desc>U+201C Left double quotation mark</desc>
          <path
            fill="#68f8f8"
            id="c"
            d="M123 366q-56 0 -89.5 -45t-33.5 -104 q0 -67 56 -136.5t153 -80.5l11 35q-59 12 -94 56t-35 85 q0 20 8 31.5t20 11.5q94 0 94 78q0 27 -23.5 48t-66.5 21z"
          />
          <use xlink:href="#c" transform="translate(230)" />
        </svg>
      </span>

      <div class="testimonials-card__content">{{ data.content }}</div>

      <div v-if="data.rating > 0" class="testimonials-card__rating">
        <rating-stars :rating="data.rating" />
      </div>
    </div>

    <div class="testimonials-card__info user">
      <span class="user__image">
        <img :src="data.image" :alt="data.username" width="50" height="50" />
      </span>
      <strong class="user__title">{{ data.username }}</strong>
      <span class="user__subtitle">{{ data.position }}</span>
    </div>
  </div>
</template>

<script>
import RatingStars from "./RatingStars.vue";

export default {
  components: {
    RatingStars,
  },

  props: {
    data: {
      type: Object,
      default: () => ({}),
    },
  },
};
</script>

<style>
.testimonials-card {
  color: var(--light-0, inherit);
  text-align: center;
  align-items: center;
}
.testimonials-card__box {
  padding: 1.25rem;
  background-color: var(--dark-1);
  border: 1px solid rgba(255, 255, 255, 0.16);
  box-shadow: var(--shadow);
}
.testimonials-card__icon {
  display: block;
  margin-inline: auto;
  margin-bottom: 1rem;
}
.testimonials-card__content {
  font-size: 0.875rem;
  font-weight: normal;
  line-height: 1.88;
  opacity: 0.9;
  margin-top: 1rem;
  margin-bottom: 1.875rem;
}
.testimonials-card__rating {
  margin-block: 1rem;
  margin-inline: auto;
}
.testimonials-card .user {
  transform: translateY(-40px);
  display: flex;
  flex-direction: column;
  align-items: center;
}
.testimonials-card .user__image {
  --size: 50px;
  width: var(--size);
  min-width: var(--size);
  height: var(--size);
  border-radius: 9999px;
  display: block;
  overflow: hidden;
}
.testimonials-card .user__image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: top;
}
.testimonials-card .user__title {
  font-size: 1rem;
  font-weight: bold;
  line-height: 1.7;
  margin-top: 0.875rem;
}
.testimonials-card .user__subtitle {
  font-size: 0.75rem;
  font-weight: normal;
  margin: 0;
}

@media (min-width: 48em) {
  .testimonials-card__box {
    padding: 1.875rem;
  }
}
</style>
