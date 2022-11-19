<template>
  <div class="dropdown-overlay" v-show="show" @click="toggle"></div>
  <div class="dropdown" :class="className" :aria-expanded="show">
    <button type="button" class="dropdown-toggle" @click.prevent="toggle">
      {{ name }}
    </button>

    <div class="dropdown-menu" :class="{ show }" :aria-hidden="!show">
      <a
        v-for="(item, index) in items"
        :key="item.id || index"
        :href="item.url || '#'"
        class="dropdown-item"
      >
        {{ item.name }}
      </a>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    name: { type: String, default: () => "" },
    items: { type: Array, default: () => [] },
    arrow: { type: Boolean, default: () => true },
    className: { type: String, default: () => "" },
  },

  data() {
    return {
      show: false,
    };
  },

  methods: {
    toggle() {
      this.show = !this.show;
    },
  },
};
</script>

<style>
.dropdown-overlay {
  position: fixed;
  inset: 0;
  /* background: rgba(0, 0, 0, 0.5); */
  background-color: transparent;
  /* cursor: pointer; */
  z-index: 10;
}
.dropdown {
  position: relative;
  --dropdown-w: 15rem;
}
.dropdown-toggle {
  outline: none;
  all: inherit;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}
.dropdown-toggle:after {
  content: "";
  display: inline-block;
  vertical-align: middle;
  --size: 20px;
  width: var(--size);
  min-width: var(--size);
  height: var(--size);
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='18' height='18' viewBox='0 0 24 24' fill='none' stroke='%2368f8f8' stroke-width='2' stroke-linecap='round' stroke-linejoin='round' class='feather feather-chevron-down'%3E%3Cpolyline points='6 9 12 15 18 9'/%3E%3C/svg%3E");
  background-size: contain;
  background-position: center;
}
.dropdown-menu {
  display: none;
  visibility: hidden;
  pointer-events: none;
  position: absolute;
  top: 100%;
  inset-inline-start: 0;
  min-width: var(--dropdown-w);
  z-index: 20;
}
.dropdown.end .dropdown-menu {
  inset-inline-start: unset;
  inset-inline-end: 0;
}
.dropdown-menu.show {
  display: block;
  visibility: visible;
  pointer-events: all;
}
.dropdown-item {
  padding: 0.75rem 1.25rem;
  background-color: inherit;
  color: inherit;
  font-size: 0.875rem;
  font-weight: 500;
  line-height: normal;
  display: block;
  width: 100%;
  transition: background var(--transition), color var(--transition);
}
</style>
