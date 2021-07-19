<template>
  <div class="film">
    <div
      class="inner"
      :style="{
        backgroundImage:
          'url(' +
          'https://image.tmdb.org/t/p/w1280' +
          film.backdrop_path +
          ')',
      }"
    >
      <div class="bg_null" v-if="film.backdrop_path == null">
        <img src="../assets/broken-1.png" alt="" />
      </div>
      <div class="details">
        <ul>
          <li>Titolo: {{ film.title }} {{ film.name }}</li>
          <li>
            Titolo originale: {{ film.original_title }} {{ film.original_name }}
          </li>
          <li>Voto: {{ film.vote_average }}</li>
          <li>Overview: {{ film.overview }}</li>
          <li class="flag">
            <span>Lingua:</span>
            <div class="flag_img">
              <img :src="'./flags/' + film.original_language + '.svg'" alt="" />
            </div>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "Film",
  props: {
    film: Object,
  },
};
</script>


<style lang="scss" scoped>
.film {
  height: 450px;
  .inner {
    height: 90%;
    position: relative;
    background-color: #ccc;
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    z-index: 1;
    .details {
      display: none;
      height: 100%;
      overflow: auto;
      z-index: 10;
      .flag_img {
        width: 40px;
        img {
          width: 100%;
        }
      }
    }
    &:hover .details {
      background-color: black;
      display: block;
    }
    .bg_null {
      position: absolute;
      height: 100%;
      width: 100%;
      img {
        width: 100%;
        height: 100%;
      }
    }
    &:hover .bg_null {
      display: none;
    }
  }
}
</style>