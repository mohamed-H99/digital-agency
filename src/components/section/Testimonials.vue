<template>
  <section class="section testimonials">
    <div class="container">
      <h2 class="section__title">Testimonials.</h2>
      <span class="section-subtitle">We are more than digital agency</span>
    </div>

    <div class="testimonials-cards">
      <swiper
        :modules="modules"
        :pagination="{ clickable: true }"
        v-bind="settings"
      >
        <swiper-slide
          v-for="(item, index) in testimonials"
          :key="item.id || index"
        >
          <testimonials-card :data="item" />
        </swiper-slide>
      </swiper>
    </div>

    <div class="container">
      <div class="logos">
        <span
          v-for="(item, index) in logos"
          :key="item.id || index"
          class="logos__item"
        >
          <img
            :src="item.url"
            :alt="item.name"
            :title="item.name"
            width="100"
            height="100"
          />
        </span>
      </div>
    </div>

    <div class="section-vertical"></div>
  </section>
</template>

<script>
import SwiperCore, { Navigation, Pagination, A11y } from "swiper";

import { Swiper, SwiperSlide } from "vue-awesome-swiper";
import TestimonialsCard from "../partials/TestimonialsCard.vue";

SwiperCore.use([Navigation, Pagination, A11y]);

export default {
  components: {
    Swiper,
    SwiperSlide,
    TestimonialsCard,
  },

  computed: {
    testimonials() {
      return [
        {
          content:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptatem doloremque voluptatibus, minima laboriosam deserunt eligendi architecto? Id dolorum quasi rerum.",
          rating: 0,
          image: "https://i.pravatar.cc/40?img=1",
          username: "John Doe",
          position: "Designation",
        },
        {
          content:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptatem doloremque voluptatibus, minima laboriosam deserunt eligendi architecto? Id dolorum quasi rerum.",
          rating: 0,
          image: "https://i.pravatar.cc/40?img=9",
          username: "John Doe",
          position: "Designation",
        },
        {
          content:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptatem doloremque voluptatibus, minima laboriosam deserunt eligendi architecto? Id dolorum quasi rerum.",
          rating: 0,
          image: "https://i.pravatar.cc/40?img=30",
          username: "John Doe",
          position: "Designation",
        },
        {
          content:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptatem doloremque voluptatibus, minima laboriosam deserunt eligendi architecto? Id dolorum quasi rerum.",
          rating: 0,
          image: "https://i.pravatar.cc/40?img=4",
          username: "John Doe",
          position: "Designation",
        },
        {
          content:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptatem doloremque voluptatibus, minima laboriosam deserunt eligendi architecto? Id dolorum quasi rerum.",
          rating: 0,
          image: "https://i.pravatar.cc/40?img=50",
          username: "John Doe",
          position: "Designation",
        },
      ];
    },
    logos() {
      return [
        { name: "Nike", url: "./logo-1.png" },
        { name: "Chanel", url: "./logo-2.png" },
        { name: "Lexus", url: "./logo-3.png" },
        { name: "Uber", url: "./logo-4.png" },
        { name: "Apple", url: "./logo-5.png" },
        { name: "Gucci", url: "./logo-6.png" },
        { name: "Miu Miu", url: "./logo-7.png" },
      ];
    },
  },

  setup() {
    return {
      modules: [Pagination],
      settings: {
        slidesPerView: 1.25,
        spaceBetween: 20,
        // loop: true,
        lazyLoading: true,
        centerMode: true,
        keyboard: {
          enabled: true,
        },

        breakpoints: {
          480: {
            slidesPerView: 1.8,
          },
          768: {
            slidesPerView: 2.8,
            spaceBetween: 30,
          },
          992: {
            slidesPerView: 3.8,
            spaceBetween: 30,
          },
        },
      },
    };
  },
};
</script>

<style>
.testimonials {
  background-color: var(--dark-2);
  color: var(--light-0);
  padding-inline-start: 1.25rem;
}

.testimonials-cards {
  margin-top: 2rem;
}

.testimonials-cards .swiper-wrapper {
  padding-bottom: 2rem;
}

.testimonials .logos {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  margin-top: 2rem;
}
.testimonials .logos__item {
  --size: 90px;
  width: var(--size);
  min-width: var(--size);
  height: var(--size);
  overflow: hidden;
}
.testimonials .logos img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

@media (min-width: 48em) {
  .testimonials {
    padding-inline-start: 1.875rem;
  }
  .testimonials-cards {
    margin-top: 3.5rem;
  }
  .testimonials .logos {
    gap: 1.375rem;
    margin-top: 3.5rem;
  }
}
@media (min-width: 62em) {
  .testimonials-cards {
    margin-top: 5rem;
  }
  .testimonials .logos {
    gap: 1.875rem;
    margin-top: 5rem;
  }
}
</style>
