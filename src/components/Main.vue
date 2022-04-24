<template>
    <main>
        <div class="container">
          <!-- here we call the component film list and serie list that will show the datas -->
            <FilmList :movies="movies"/>
            <SerieList :series="series"/>
        </div>
    </main>
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

main {
  background-color: grey;
  min-height: 100vh;
}

</style>