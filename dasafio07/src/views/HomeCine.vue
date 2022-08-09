<template>
  <div>
    <navList />
    <MovieHead />

</div>
</template>
<script>
import navList from "../components/navList.vue"
import MovieHead from "../components/MovieHead.vue"

export default {
  components: {
    navList,
    MovieHead,

  },

};
</script>
<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  color: white;
  font-family: Arial, Helvetica, sans-serif;
  background-image: linear-gradient(315deg, #485461 0%, #28313b 74%); 
  background-repeat: no-repeat;
  height: 5vw;
}
</style>