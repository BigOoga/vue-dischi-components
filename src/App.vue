<template>
  <div id="app">
    <Header />
    <Main />
  </div>
</template>

<script>
import Header from "@/components/Header";
import Main from "@/components/Main";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/style.scss";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
