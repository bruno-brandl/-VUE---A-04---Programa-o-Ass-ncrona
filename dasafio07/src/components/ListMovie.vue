<template>
  <div class="list">
    <h1>LISTA DE FILMES:</h1>
    <div class="user">

      <a id="ano">Ano</a>
      <a id="filmes">Filmes</a>
    </div>
    <div id="renderResult">

      <ul v-for="filme in filmes" :key="filme.id">
        <li id="content-filme" >{{ filme.name }}  </li>
      </ul>
    </div>
  </div>
</template>
<script>

import axios from "axios";

export default {
  data() {
    return {
      filmes: []
    };
  },
  async created() {
    try {
      const response = await axios.get(`http://localhost:3000/filmes`);
      const dataFilmes = response.data;
      this.filmes = dataFilmes
    } catch (e) {
      console.error(e);
    }
  }
};
</script>

<style scoped>
.list {
  padding: 3vw;
  height: 43vw;
}

#ano {
  margin-left: 19%;
}

#filmes {
  margin-left: 294px;
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
  margin-left: 0vw;
}

#content-filme {
  margin-left: -28%;
  margin-top: 2vw;

}

h1 {
  margin-left: 12vw;
  margin-top: 4vh;
  margin-bottom: 4vh;
}
</style>  