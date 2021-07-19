<template>
  <header class="">
    <div class="container-fluid">
      <div class="row justify-content-between align-items-center">
        <div class="col-5 d-flex align-items-center">
          <div class="logo">
            <img src="../assets/2560px-Netflix_2015_logo.svg.png" alt="logo" />
          </div>
          <div class="commands">
            <ul class="d-flex">
              <li><a href="#">Home</a></li>
              <li><a href="#">Serie TV</a></li>
              <li><a href="#">Film</a></li>
              <li><a href="#">Originali</a></li>
              <li><a href="#">Aggiunti di recente</a></li>
              <li><a href="#">La mia lista</a></li>
            </ul>
          </div>
        </div>
        <div class="col-3 d-flex align-items-center right_commands">
          <div class="input_film d-flex align-items-center">
            <input
              v-model="inputString"
              placeholder="Cerca un film o serie"
              type="text"
            />
            <i
              @click="$emit('selectFilm', inputString)"
              class="fas fa-search search_button"
            ></i>
          </div>
          <div class="category">Bambini</div>
          <div class="notify"><i class="fas fa-bell"></i></div>
          <div class="profile">
            <img src="../assets/profile.png" alt="" />
          </div>
          <div class="select_profile"><i class="fas fa-sort-down"></i></div>
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
  .commands {
    ul {
      li {
        margin-right: 10px;
      }
    }
  }
  .profile {
    img {
      width: 40px;
    }
  }
  .right_commands {
    * {
      margin-right: 10px;
    }
  }
}
.input_film {
  input {
    color: black;
  }
  .search_button:hover {
    cursor: pointer;
  }
  * {
    margin-right: 10px;
  }
}

.container-fluid {
  height: 100%;
  .row {
    height: 100%;
  }
}
</style>