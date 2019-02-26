<template>
  <div>
    <h1>Create Event, {{ user.name }}</h1>
    <p>This event was created by {{ user.name }}</p>
    <p>There are {{ catLength }} categories</p>
    <p>{{ getEvent(1) }}</p>
    <ul>
      <li v-for="cat in categories" :key="cat">
        {{ cat }}
      </li>
    </ul>
  </div>
</template>

<script>
import { mapState } from "vuex";
export default {
  computed: {
    catLength: state => {
      return state.categories.length;
    },
    ...mapState(["categories", "user"]),
    getEvent() {
      return this.$store.getters.getEventById;
    }
  }
};
</script>

<style></style>
