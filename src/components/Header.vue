<template>
  <header class="">
    <div class="container-fluid">
      <div class="row justify-content-between align-items-center">
        <div class="col-4 d-flex align-items-center">
          <div class="logo">
            <img src="../assets/2560px-Netflix_2015_logo.svg.png" alt="logo" />
          </div>
          <div class="commands">
            <ul class="d-flex">
              <li><a href="#">home</a></li>
              <li><a href="#">home</a></li>
              <li><a href="#">home</a></li>
              <li><a href="#">home</a></li>
              <li><a href="#">home</a></li>
              <li><a href="#">home</a></li>
              <li><a href="#">home</a></li>
            </ul>
          </div>
        </div>
        <div class="col-2 d-flex align-items-center">
          <div class="input_film">
            <input
              v-model="inputString"
              placeholder="cerca un film"
              type="text"
              @keyup="$emit('selectFilm', inputString)"
            />
            <button @click="ricercaFilm()">Premi</button>
          </div>
          <div class="category">Bambini</div>
          <div class="notify"></div>
          <div class="profile">
            <img src="../assets/profile.png" alt="" />
          </div>
          <div class="select_profile">v</div>
        </div>
      </div>
    </div>
  </header>
</template>




<script>
export default {
  name: "Header",
  props: {
    ricercaFilm: Function,
  },
  data() {
    return {
      inputString: "",
    };
  },
};
</script>



<style lang="scss" scoped>
header {
  height: 100px;
  background-color: black;
  .logo {
    img {
      width: 200px;
    }
  }
  .profile {
    img {
      width: 100%;
    }
  }
}
.input_film {
  input {
    color: black;
  }
}

.container-fluid {
  height: 100%;
  .row {
    height: 100%;
  }
}
</style>