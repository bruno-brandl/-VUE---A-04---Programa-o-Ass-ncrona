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
          <li @click="ModalOpen"><i class="fa fa-eye" id="icon" aria-hidden="true"></i> </li>
        </ul>
      </div>
      <ModalMovie :User_Prop="User_Prop" v-show="openModal" />
    </div>

  </div>
</template>
<script lang="ts">
import axios from "axios";
import ModalMovie from "../components/ModalMovie.vue"
import navList from "../components/navList.vue"
import { Component, Vue } from "vue-property-decorator";
@Component({
  components: {
    ModalMovie,
    navList,
  }
})
export default class MovieList extends Vue {
  openModal = false
  filmes = [{}]
  User_Prop = [{}]
  ModalOpen() {
    if (!this.openModal) {
      this.openModal = true
       this.User_Prop = this.filmes
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
  margin-left: 13vw;
}

#renderResult {
  width: 80vw;
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
  margin-left: 0vw;
  margin-right: 24vw;
}

#content-filme {
  margin-left: -28%;
  margin-top: 0vw;

}

h1 {
  margin-left: 12vw;
  margin-top: 4vh;
  margin-bottom: 4vh;
}
</style>