<template>
  <div class="list">
    <h1>LISTA DE FILMES:</h1>
    <div class="user">

      <a id="cpf">Ano</a>
      <a id="FullName">Filmes</a>
    </div>
    <div id="renderResult">

      <ul>

        <li id="content-cpf"><br>22/09/2004</li>

        <li id="content-name">O Tomate </li>
        
        <li><i class="fa fa-eye" id="icon" aria-hidden="true"></i> </li>
      </ul>
    </div>
  </div>
</template>
<script>

</script>

<style scoped>
.list{
    padding: 4vw;
}
hr {
  margin-left: 13%;
  margin-right: 18%;
}

#cpf {
  margin-left: 19%;
}

#FullName {
  margin-left: 294px;
}

.pagination {
  cursor: pointer;
  position: static;
  margin-left: 23vw;
  list-style: none;
  display: inline-flex;
  width: 50vw;
  justify-content: space-between;
  font-size: 22px;
  
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
  margin-left: 2vw;
}

#content-name {
  margin-left: -20%;
  margin-top: 2vw;

}
h1{
  margin-left: 12vw;
  margin-top: 4vh;
  margin-bottom: 4vh;
}
</style>  