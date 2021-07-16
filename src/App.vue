<template>
  <div id="app">
    <Header :ricercaFilm()="ricercaFilm()" @selectFilm="searchFilmInput" />
    <Main :filmsProva="filmsProva" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },
  data() {
    return {
      filmsProva: [],
      inputSearch: "",
      apiKey: "9d83a4b95efc96bb81b4c69059220181",
      apiUrl: "https://api.themoviedb.org/3/search/movie?",
    };
  },
  /*created() {
    axios
      .get(
        "https://api.themoviedb.org/3/search/movie?api_key=9d83a4b95efc96bb81b4c69059220181&query=ritorno+al+futuro"
      )
      .then((result) => {
        this.filmsProva = result.data.results;
      });
  },*/
  methods: {
    searchFilmInput: function (inputString) {
      this.inputSearch = inputString.trim();
    },
    ricercaFilm: function () {
      const request = {
        params: {
          api_key: this.apiKey,
          query: this.inputSearch,
        },
      };
      axios.get(this.apiUrl, request).then((result) => {
        this.filmsProva = result.data.results;
      });
    },
  },
};
</script>

<style lang="scss">
@import "./style/app.scss";
</style>
