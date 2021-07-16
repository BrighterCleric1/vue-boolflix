<template>
  <main>
    <div class="container-fluid">
      <div class="row main_title">
        <div class="col">
          <h1>ORIGINALI NETFLIX</h1>
        </div>
        <div class="row films">
          <Film
            class="col-2"
            v-for="(film, index) in filmsProva"
            :key="index"
            :film="film"
          />
        </div>
      </div>
    </div>
  </main>
</template>




<script>
import Film from "./Film.vue";
export default {
  name: "Main",
  props: {
    filmsProva: Array,
  },
  components: {
    Film,
  },
};
</script>



<style lang="scss" scoped>
main {
  background-color: #303030;
}
</style>