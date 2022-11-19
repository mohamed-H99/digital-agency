<template>
  <div class="side-menu" :class="{ show }">
    <div class="side-menu__header">
      <span></span>

      <button type="button" class="side-menu__toggler" @click="hide">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="20"
          height="20"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="feather feather-x"
        >
          <line x1="18" y1="6" x2="6" y2="18" />
          <line x1="6" y1="6" x2="18" y2="18" />
        </svg>
      </button>
    </div>

    <div class="side-menu__wrapper">
      <div class="links">
        <a
          v-for="(item, index) in navLinks"
          :key="index"
          :href="item.url || '#'"
        >
          {{ item.name }}
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  computed: {
    navLinks() {
      return [
        { name: "Works", url: "" },
        { name: "About", url: "" },
        { name: "Blog", url: "" },
      ];
    },
    homeItems() {
      return [
        { name: "Demo 1", url: "" },
        { name: "Demo 2", url: "" },
        { name: "Demo 3", url: "" },
      ];
    },
    servicesItems() {
      return [
        { name: "Demo 1", url: "" },
        { name: "Demo 2", url: "" },
        { name: "Demo 3", url: "" },
      ];
    },
    contactItems() {
      return [
        { name: "Demo 1", url: "" },
        { name: "Demo 2", url: "" },
        { name: "Demo 3", url: "" },
      ];
    },
  },

  methods: {
    hide() {
      document.body.classList.remove("side-menu--open");
    },
  },
};
</script>

<style>
.side-menu {
  position: fixed;
  inset: 0;
  background-color: var(--headerBgColor, var(--dark-0));
  color: var(--headerTextColor, var(--light-0));
  z-index: 90;
  transform: translateY(105%);
  transition: transform var(--transition-l);
}
.side-menu--open .side-menu {
  transform: translateY(0%);
}
.side-menu__header {
  padding: 0.5rem 1rem;
  margin-bottom: 0.5rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 0.75rem;
}
.side-menu a {
  text-decoration: none;
  color: inherit;
  font-size: 1rem;
  display: block;
  width: 100%;
  padding: 0.75rem 1.25rem;
  transition: color var(--transition), background-color var(--transition);
}
.side-menu a:hover {
  background-color: var(--headerPrimaryColor, var(--primary-0));
  color: var(--headerBgColor, var(--dark-0));
}
.side-menu__toggler {
  border: 2px solid var(--headerPrimaryColor, var(--primary-0));
  border-radius: 9999px;
  --size: 40px;
  width: var(--size);
  min-width: var(--size);
  height: var(--size);
  background-color: transparent;
  color: var(--headerPrimaryColor, var(--primary-0));
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
