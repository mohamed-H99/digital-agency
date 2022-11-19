<template>
  <header class="app-header">
    <search-box />

    <nav class="navbar">
      <div class="container navbar__wrapper">
        <!-- logo -->
        <a
          href="#"
          class="navbar__logo uppercase"
          aria-label="ZAMIL"
          title="Homepage"
        >
          <strong>ZAMIL</strong>
        </a>

        <!-- links -->
        <div class="navbar__links desktop-view">
          <dropdown name="Home" className="end" :items="homeItems" />
          <dropdown name="Services" className="end" :items="servicesItems" />

          <a
            v-for="(item, index) in navLinks"
            :key="item.id || index"
            :href="item.url || '#'"
            class="link"
          >
            {{ item.name }}
          </a>

          <dropdown
            name="Contact"
            className="featured end"
            :items="contactItems"
          />

          <button
            type="button"
            class="navbar__toggler border-0"
            @click="toggleSearch"
          >
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
              class="feather feather-search"
            >
              <circle cx="11" cy="11" r="8" />
              <line x1="21" y1="21" x2="16.65" y2="16.65" />
            </svg>
          </button>
        </div>

        <!-- toggler -->
        <div class="navbar__togglers mobile-view">
          <button type="button" class="navbar__toggler" @click="toggleSearch">
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
              class="feather feather-search"
            >
              <circle cx="11" cy="11" r="8" />
              <line x1="21" y1="21" x2="16.65" y2="16.65" />
            </svg>
          </button>
          <button type="button" class="navbar__toggler" @click="openSidemenu">
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
              class="feather feather-menu"
            >
              <line x1="3" y1="12" x2="21" y2="12" />
              <line x1="3" y1="6" x2="21" y2="6" />
              <line x1="3" y1="18" x2="21" y2="18" />
            </svg>
          </button>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
import Dropdown from "./Dropdown.vue";
import SearchBox from "./SearchBox.vue";

export default {
  components: {
    Dropdown,
    SearchBox,
  },

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
    openSidemenu() {
      document.body.classList.add("side-menu--open");
    },
    toggleSearch() {
      document.body.classList.toggle("search-box--open");
    },
  },
};
</script>

<style>
.app-header {
  --headerBgColor: var(--dark-0);
  --headerTextColor: var(--light-0);
  --headerPrimaryColor: var(--primary-0);

  background-color: var(--headerBgColor);
  color: var(--headerTextColor);
}

.navbar__wrapper {
  padding-block: 0.5rem;
  color: inherit;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 0.625rem;
}

.navbar .featured {
  color: var(--headerPrimaryColor);
}
.navbar__logo {
  font-size: 2rem !important;
  font-weight: bold !important;
  text-decoration: none;
  color: inherit;
}

.navbar__togglers {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.navbar__toggler {
  border: 2px solid var(--headerPrimaryColor);
  border-radius: 9999px;
  --size: 40px;
  width: var(--size);
  min-width: var(--size);
  height: var(--size);
  background-color: transparent;
  color: var(--headerPrimaryColor);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
}

.navbar__links {
  display: flex;
  align-items: center;
}

.navbar .dropdown-menu {
  background-color: var(--headerTextColor);
  color: var(--headerBgColor);
  border: 2px solid var(--headerBgColor);
  display: block;
  visibility: visible;
  opacity: 0;
  pointer-events: none;
  transform: translateY(1rem);
  transition: opacity var(--transition), transform var(--transition);
}
.navbar .dropdown-menu.show {
  opacity: 1;
  pointer-events: all;
  transform: translateY(0);
}
.navbar .dropdown-item:hover {
  background-color: var(--light-1);
  opacity: 1;
}

.navbar a:not(.dropdown-item, .navbar__logo),
.navbar .dropdown-toggle {
  text-decoration: none;
  color: inherit;
  font-size: 0.75rem;
  font-weight: bold;
  border: 2px solid transparent !important;
  transition: transform var(--transition), color var(--transition),
    background-color var(--transition);
  padding: 1.25rem 0.75rem;
  text-transform: uppercase;
}
/* .navbar a:not(.dropdown-item, .navbar__logo):hover,
.navbar .dropdown-toggle:hover,
.navbar .dropdown[aria-expanded="true"] .dropdown-toggle {
  opacity: 0.9;
  border-bottom-color: var(--headerPrimaryColor) !important;
  color: var(--headerBgColor);
} */
.navbar .dropdown.featured {
  margin-inline: 0.5rem;
}
.navbar .dropdown.featured .dropdown-toggle {
  padding-block: 0.5rem;
}
.navbar .dropdown.featured .dropdown-toggle {
  border: 2px solid var(--headerPrimaryColor) !important;
  padding-inline: 0.75rem;
}
.navbar .dropdown.featured .dropdown-toggle:active {
  transform: scale(0.95);
}
</style>
