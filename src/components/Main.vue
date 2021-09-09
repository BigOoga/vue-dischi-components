<template>
  <main class="container">
    <Selection />
    <AlbumContainer />
  </main>
</template>

<script>
import AlbumContainer from "@/components/AlbumContainer";
import Selection from "@/components/Selection.vue";

export default {
  name: "Main",
  components: {
    AlbumContainer,
    Selection,
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/style.scss";
</style>
