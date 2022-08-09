<template>
  <div class="about">
    <navList />
    <div class="list">
      <h1>LISTA DE FILMES:</h1>
      <div class="user">

        <a id="ano">Ano</a>
        <a id="filmes">Filmes</a>
      </div>
      <div id="renderResult">
        <ul v-for="filme in filmes" :key="filme.id">
          <li id="content-ano">{{ filme.ano }}</li>
          <li id="content-filme">{{ filme.name }} </li>
          <li @click="ModalOpen(filme)"><img id="svg" :src="editSvg" alt=""></li>
          <li @click="edit"><img :src="iconSvg" alt=""></li>
        </ul>
      </div>
      <ModalMovie :user_Prop="user_Prop" v-show="openModal" />
      <modalEdit v-show="EditModal"/>
    </div>

  </div>
</template>
<script lang="ts">
import axios from "axios";
import ModalMovie from "../components/ModalMovie.vue"
import navList from "../components/navList.vue"
import modalEdit from "../components/modalEdit.vue"
import { Component, Vue } from "vue-property-decorator";
@Component({
  components: {
    ModalMovie,
    navList,
    modalEdit
  }
})
export default class MovieList extends Vue {
  openModal = false
  EditModal = false
  filmes = [{}]
  user_Prop = {}
  editSvg = require('../assets/eye.svg')
  iconSvg = require('../assets/iconEdit.svg')
  edit(){
    if(!this.EditModal){
      this.EditModal = true
    }
  }
  ModalOpen(MovieCheck: object) {
    this.user_Prop = MovieCheck
    if (!this.openModal) {
      this.openModal = true
    }
  }
  async created() {
    try {
      const response = await axios.get(`http://localhost:3000/filmes`);
      this.filmes = response.data
    } catch (e) {
      console.error(e);
    }
  }
}
</script>

<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  background-color: #6c6a6b;
  color: white;
  font-family: Arial, Helvetica, sans-serif;
}

.list {
  padding: 3vw;
  height: 43vw;
}

#ano {
  margin-left: 19%;
}

#filmes {
  margin-left: 19vw;
}

#renderResult {
  width: 64vw;
  margin-top: 28px;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  margin-left: 15vw;
}

ul {
  display: flex;
  padding: 5px;
  align-items: center;
  justify-content: space-between;
}

ul li {
  font-size: 19px;
  list-style-type: none;
}

#content-filme {
    margin-left: 7%;
    margin-top: 0vw;
    width: 11vw;
}

h1 {
  margin-left: 12vw;
  margin-top: 4vh;
  margin-bottom: 4vh;
}
</style>