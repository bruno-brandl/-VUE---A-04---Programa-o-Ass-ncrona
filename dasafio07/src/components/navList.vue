<template>
  <header>
    <div class="navbar">
      <div class="nav-container">
        <a href="https://warren.com.br/?utm_source=google&utm_medium=cpc&utm_campaign=ppc-warren_google_cpc_search_conversao_marca_key&utm_adgroup=marca&gclid=CjwKCAjwkYGVBhArEiwA4sZLuBX4iNmO8grMnu5ulmiZZSx_pPMa_1DKeITbs5nXzB7Nxoq62vwhVxoCZrAQAvD_BwE">
        </a>
        <ul>
        <a class="menu">Adicionar Filme</a>

          <div class="dropdown">
            <a class="dropbtn">Curiosidades</a>
            <div class="dropdown-content">
              <a href="#">Link 1</a>
              <a href="#">Link 2</a>
              <a href="#">Link 3</a>
            </div>
          </div>
          <a class="menu">Lista de Filmes</a>
         <router-link to="/"> <a class="menu" >Home</a></router-link>
          <router-link to="/list"><a class="botao" >Lista de Filmes</a></router-link>  
        </ul>
      </div>
    </div>
  </header>
</template>
<script>

</script>
<style>
.dropbtn {
  color: rgb(0, 0, 0);
  padding: 16px;
  font-size: 19px;
  border: none;
  cursor: pointer;
  font-family: "Source Sans Pro", sans-serif;
}
.dropdown {
  position: relative;
  display: inline-block;
}
.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
}
.dropdown-content a {
  color: black;
  display: block;
}
.dropdown-content a:hover {
  background-color: #f1f1f1;
}
.dropdown:hover .dropdown-content {
  display: block;
}
.dropdown:hover .dropbtn {
  border-bottom: 2px solid rgb(0, 0, 0);
}
* {
  box-sizing: border-box;
  margin: 0;
}
.logo {
  cursor: pointer;
}
.logo:hover {
  -ms-transform: scale(1.2);
  -webkit-transform: scale(1.2);
  transform: scale(1.2);
}
.navbar {
  background-color: #857f81;
  padding-top: 1rem;
  padding-bottom: 1rem;
  width: 100%;
}
.nav-container {
  font-family: "Source Sans Pro", sans-serif;
  justify-content: center;
  display: flex;
}
.menu {
  color: #000000;
  font-size: 19px;
  line-height: 32px;
  margin: 74px;
  text-decoration: none;
  border-radius: 5px;
}
.menu:hover {
  border-radius: 5px;
  color: rgb(255, 255, 255);
  text-decoration: underline;
  text-decoration-color: rgb(92, 96, 92);
  border-bottom: 8px solid rgb(22, 21, 21);
}
.botao {
  margin-left: 50px;
  text-decoration: none;
  color: #ffffff;
  padding: 13px;
  border-radius: 24px;
  background-color: black;
  cursor: pointer;

}
.botao:hover {
  background-color: #f5e6e6;
  color: rgb(0, 0, 0);
}
</style>