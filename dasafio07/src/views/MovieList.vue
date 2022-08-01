<template>
  <div class="about">
    <navList />
    <ListMovie />

  </div>
</template>
<script>
import ListMovie from "../components/ListMovie.vue"
import navList from "../components/navList.vue"

export default {
  components: {
    ListMovie,
    navList,
  },

};
</script>
<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  background-color: #6c6a6b;
  color: white;
  font-family: Arial, Helvetica, sans-serif;
}

</style>
