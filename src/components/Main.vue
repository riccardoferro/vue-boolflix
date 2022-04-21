<template>
    <div class="container">
        <h2>FILM</h2>
        <FilmList :movies="movies"/>
        <h2>SERIE</h2>
        <SerieList :series="series"/>
    </div>
</template>

<script>

import FilmList from "@/subcomponents/FilmList.vue"
import SerieList from "@/subcomponents/SerieList.vue"

export default {
  name: "MainComponent",
  props: {
    movies: Array,
    series: Array,
  },
  components: {
    FilmList,
    SerieList,
  }
}
</script>

<style lang="scss" scoped>



</style>