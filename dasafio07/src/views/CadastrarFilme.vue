<template>
<div>
    <navList/>
    <MovieRegister/>
</div>
</template>
<script>
import navList from "../components/navList.vue"
import MovieRegister from "../components/MovieRegister.vue"
export default {
  components: {
    navList,
    MovieRegister
  },

};

</script>
<style scoped>
div{
  background-color: #485461;
  background-image: linear-gradient(315deg, #485461 0%, #28313b 74%); 
  background-repeat: no-repeat;
  height: 40vw;
}
</style>