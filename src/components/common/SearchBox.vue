<template>
  <div class="search-box">
    <div class="search-box__wrapper">
      <form @submit.prevent="search">
        <input
          type="search"
          class="form-control"
          v-model.trim="searchValue"
          placeholder="Search"
        />
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchValue: "",
    };
  },

  methods: {
    search() {},
  },
};
</script>

<style>
.search-box {
  max-height: 0px;
  overflow: hidden;
  transition: max-height var(--transition-l);
}
.search-box--open .search-box {
  max-height: 100px;
}
.search-box .form-control {
  display: block;
  width: 100%;
  border: 0;
  outline: none;
  font-size: 1.5rem;
  padding-block: 0.75rem;
  padding-inline: 1rem;
  font-weight: bold;
  line-height: normal;
  color: var(--headerBgColor, var(--black-0));
  border-bottom: 3px solid var(--headerPrimaryColor, var(--primary-0));
}
.search-box .form-control::placeholder {
  color: var(--headerBgColor, var(--black-0));
}

@media (min-width: 48em) {
  .search-box .form-control {
    padding-block: 0.875rem;
    padding-inline: 5%;
    font-size: 2rem;
  }
}
</style>
