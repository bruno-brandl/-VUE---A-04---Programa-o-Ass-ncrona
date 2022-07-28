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
  background-color: #6c6a6b;

}
</style>