<template>
  <div class="film">
    <div
      class="inner"
      :style="{
        backgroundImage:
          'url(' + 'https://image.tmdb.org/t/p/w1280' + film.poster_path + ')',
      }"
    >
      <div class="bg_null" v-if="film.poster_path == null">
        <img src="../assets/broken-1.png" alt="" />
      </div>
      <div class="details">
        <ul>
          <li>
            <span class="inner_detail">Titolo: </span> {{ film.title }}
            {{ film.name }}
          </li>
          <li>
            <span class="inner_detail">Titolo originale: </span>
            {{ film.original_title }} {{ film.original_name }}
          </li>
          <li>
            <span class="inner_detail">Voto: </span>
            <i
              v-for="(stars, index) in Math.floor(film.vote_average / 2)"
              :key="index"
              class="fas fa-star stars"
            ></i>
            <i
              v-if="(film.vote_average / 2) % 1 >= 0.5"
              class="fas fa-star-half-alt stars"
            ></i>
          </li>
          <li>
            <span class="inner_detail">Overview: </span> {{ film.overview }}
          </li>
          <li class="flag d-flex align-items-center">
            <span class="inner_detail">Lingua: </span>
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
  height: 500px;
  .inner {
    height: 90%;
    position: relative;
    background-color: #ccc;
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    z-index: 1;
    .details {
      padding-top: 40px;
      display: none;
      height: 100%;
      overflow: auto;
      z-index: 10;
      .flag {
        margin-top: 20px;
      }
      ul {
        li {
          color: #777777;
        }
      }
      .stars {
        color: #ed8a19;
      }
      .inner_detail {
        font-weight: bold;
      }
      .flag_img {
        width: 40px;
        margin-left: 10px;
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