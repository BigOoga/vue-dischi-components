<template>
  <select @change="startFilter" v-model="key" name="">
    <option value="All">All</option>
    <option v-for="(genre, index) in genres" :value="genre" :key="index">
      {{ genre }}</option
    >
  </select>
</template>

<script>
export default {
  name: "Selection",
  props: {
    genres: Array,
  },
  data() {
    return {
      key: "All",
    };
  },
  methods: {
    startFilter() {
      this.$emit("startFilter", this.key);
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/style.scss";
</style>
