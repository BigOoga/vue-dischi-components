<template>
  <div>
    <Selection @startFilter="filterDiscsBy" :genres="allGenres" />
    <section id="album-container">
      <Card v-for="(disc, index) in displayDiscs" :key="index" :disc="disc" />
    </section>
  </div>
</template>

<script>
import Card from "@/components/Card.vue";
import Selection from "@/components/Selection.vue";
import axios from "../../node_modules/axios";
export default {
  name: "AlbumContainer",
  components: {
    Card,
    Selection,
  },
  data() {
    return {
      apiURI: "https://flynn.boolean.careers/exercises/api/array/music",
      discs: [],
      displayDiscs: [],
    };
  },
  computed: {
    allGenres() {
      const allGenres = [];
      this.discs.forEach((element) => {
        if (!allGenres.includes(element.genre)) {
          allGenres.push(element.genre);
        }
      });
      return allGenres;
    },
  },
  methods: {
    fetchDiscs() {
      console.log(`Fetching Discs...`);
      axios.get(this.apiURI).then((res) => {
        const response = res.data.response;

        this.discs = response;
        this.displayDiscs = response;
        this.sortDiscsByYear();
      });
    },

    filterDiscsBy(key) {
      console.log(`Filtering Discs by ${key}`);
      const filteredDiscs = [];
      if (key === "All") {
        this.displayDiscs = this.discs;
      } else {
        this.discs.forEach((element) => {
          if (element.genre === key) {
            filteredDiscs.push(element);
          }
        });
        this.displayDiscs = filteredDiscs;
      }
    },

    sortDiscsByYear() {
      console.log(`Sorting Discs by year...`);
      this.displayDiscs = this.displayDiscs.sort((a, b) => b.year - a.year);
      console.log(`Sorted.`);
    },
  },
  created() {
    this.fetchDiscs();
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/style.scss";
</style>
