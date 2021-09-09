<template>
  <main class="container">
    <AlbumContainer />
  </main>
</template>

<script>
import AlbumContainer from "@/components/AlbumContainer";

export default {
  name: "Main",
  components: {
    AlbumContainer,
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/style.scss";
</style>
