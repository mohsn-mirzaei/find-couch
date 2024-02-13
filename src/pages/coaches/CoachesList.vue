<template>
  <section>Filter</section>
  <section>
    <div class="control">
      <button>Refresh</button>
      <router-link to="/register">Register as coach</router-link>
    </div>
    <ul v-if="hasCoaches">
      <li v-for="coach in filterCoaches" :key="coach.id">
        {{ coach.firstName }}
      </li>
    </ul>
    <h3 v-else>No coaches found.</h3>
  </section>
</template>

<script>
export default {
  computed: {
    filterCoaches() {
      return this.$store.getters['coaches/coaches'];
    },
    hasCoaches() {
      return this.$store.getters['coaches/hasCoaches'];
    },
  },
};
</script>
