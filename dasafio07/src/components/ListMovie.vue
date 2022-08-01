<template>
  <div class="list">
    <h1>LISTA DE FILMES:</h1>
    <div class="user">

      <a id="ano">Ano</a>
      <a id="filmes">Filmes</a>
    </div>
    <div id="renderResult">

      <ul>

        <li id="content-ano"><br>22/09/2004</li>

        <li id="content-filme">O Tomate </li>
        
        <li><i class="fa fa-eye" id="icon" aria-hidden="true"></i> </li>
      </ul>
    </div>
  </div>
</template>
<script>

</script>

<style scoped>
.list{
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
h1{
  margin-left: 12vw;
  margin-top: 4vh;
  margin-bottom: 4vh;
}
</style>  