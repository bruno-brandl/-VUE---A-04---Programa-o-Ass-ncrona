<template>
  <div class="container">
    <div class="container-text">
      <h1>Bem Vindo(a) ao Cine Movie</h1>
      <p>Aqui você Pode Adicionar ou Assistir Filmes </p>
    </div>
    <div>
      <router-link to="/cadastro"> <button class="btn">Cadastrar Novo Filme</button></router-link>
     </div>
  </div>
</template>
<script>

</script>
<style scoped>
.container {
  width: 100%;
  height: 43vw;
  padding: 58px;
  display: flex;
  align-items: center;
  justify-content: space-around;
  color: white;
  background-color: #6c6a6b;
  border-bottom: solid 12px #6c6a6b;
}

h1 {
  font-size: 50px;

}

.btn {
  border: solid 2px rgb(230, 230, 230);
  background-color: rgb(152, 152, 152);
  color: rgb(0, 0, 0);
  padding: 16px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 20px;
  margin: 16px 2px;
  transition-duration: 0.4s;
  cursor: pointer;
  border-radius: 11px;
  height: 82px;
  width: 305px;
}

.btn:hover {
  background-color: black;
  color: rgb(255, 255, 255);
}
</style> 