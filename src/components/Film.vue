<template>
  <div class="film">
    <div class="inner">
      <div class="details">
        <ul>
          <li>Titolo: {{ film.title }}</li>
          <li>Titolo originale: {{ film.original_title }}</li>
          <li>Voto: {{ film.vote_average }}</li>
          <li>Overview: {{ film.overview }}</li>
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
  height: 600px;
  .inner {
    height: 90%;

    background-color: #ccc;
    background-image: url("https://image.tmdb.org/t/p/w342/hQq8xZe5uLjFzSBt4LanNP7SQjl.jpg");
    background-repeat: no-repeat;
    background-size: cover;
    z-index: 1;
    .details {
      display: none;
      height: 100%;
      overflow: auto;
      z-index: 10;
    }
  }
  &:hover .details {
    background-color: black;
    display: block;
  }
  &:hover .inner {
  }
}
</style>