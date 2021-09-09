<template>
  <div class="card">
    <img :src="disc.poster" :alt="disc.title" />
    <h2 class="title">{{ disc.title }}</h2>
    <address class="author">{{ disc.author }}</address>
    <time :datetime="disc.year" class="year">{{ disc.year }}</time>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    disc: Object,
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/style.scss";
</style>
