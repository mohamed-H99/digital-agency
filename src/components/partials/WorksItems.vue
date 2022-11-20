<template>
  <div class="works-items">
    <swiper v-bind="settings">
      <swiper-slide v-for="(item, index) in items" :key="item.id || index">
        <div class="works-item stop-propagation">
          <div class="works-item__image">
            <picture>
              <img
                class=""
                :src="item.image"
                :alt="item.name"
                width=""
                height=""
              />
            </picture>
          </div>

          <div class="works-item__content">
            {{ item.name }}
          </div>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "vue-awesome-swiper";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },

  props: {
    items: {
      type: Array,
      default: () => [],
    },
  },

  setup() {
    return {
      settings: {
        slidesPerView: 2.25,
        spaceBetween: 0,
        loop: true,
        lazyLoading: true,
        keyboard: {
          enabled: true,
        },

        breakpoints: {
          768: {
            slidesPerView: 4.25,
          },
          992: {
            slidesPerView: 6,
          },
        },
      },
    };
  },
};
</script>

<style>
.works-items {
  margin-block: 2rem;
}

.works-item {
  --ratio: 1/1.5;
  position: relative;
  overflow: hidden;
  width: 100%;
  height: auto;
}
.works-item:hover .works-item__image,
.works-item:focus .works-item__image {
  opacity: 0.4;
  transform: scale(0.95);
}
.works-item__content {
  position: absolute;
  top: 70%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-weight: bold;
  font-size: 1.5rem;
  transition: opacity var(--transition-l), top var(--transition-l);
  opacity: 0;
}
.works-item:hover .works-item__content,
.works-item:focus .works-item__content {
  opacity: 1;
  top: 50%;
}
.works-item__image {
  transition: opacity var(--transition-l), transform var(--transition-l);
  aspect-ratio: var(--ratio);
  width: 100%;
  height: auto;
}
.works-item__image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

@media (min-width: 48em) {
  .works-items {
    margin-block: 3.5rem;
  }
}
@media (min-width: 62em) {
  .works-items {
    margin-block: 5rem;
  }
}
</style>
