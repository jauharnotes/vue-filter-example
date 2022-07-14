<template>
  <h2>Filters</h2>

  <!-- <form action=""></form> -->
  <input type="text" v-model="term" @keypress.enter="search(term)" />

  <a
    class="category"
    v-for="filter in filters"
    :key="filter"
    @click="filterPost(filter)"
  >
    {{ filter }}
  </a>
</template>

<script>
const filters = ['HVAC', 'Overhead Doors', 'ALL'];

export default {
  props: ['filterPost', 'search'],
  data() {
    return {
      filters,
      term: '',
    };
  },
  created() {
    console.log(this.term);
  },
};
</script>

<style scoped>
.category {
  display: block;
  text-decoration: none;
  color: green;
  cursor: pointer;
}
</style>
