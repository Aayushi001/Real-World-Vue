<template>
  <div>
    <h1>Create Event, {{user.name}}</h1>
    <p>There are {{catLength}} categories</p>
    <ul>
      <li v-for="cat in categories" :key="cat">{{cat}}</li>
    </ul>
    <p>{{getEventById(2)}}</p>
  </div>
</template>

<script>
import { mapState, mapGetters } from "vuex";
export default {
  computed: {
    catLength() {
      return this.$store.getters.catLength;
    },
    ...mapGetters(["getEventById"]),
    ...mapState(["user", "categories"])
  }
};
</script>

<style lang="scss" scoped>
</style>