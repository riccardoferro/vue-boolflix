<template>
    <div class="container">
        <h2>FILM</h2>
        <FilmList :movies="movies"/>
    </div>
</template>

<script>

import FilmList from "@/subcomponents/FilmList.vue"

export default {
  name: "MainComponent",
  props: {
    movies: Array
  },
  components: {
    FilmList
  }
}
</script>

<style lang="scss" scoped>



</style>