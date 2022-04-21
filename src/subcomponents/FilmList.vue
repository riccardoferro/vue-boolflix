<template>
    <div class="row d-flex">
        <div v-for="movie in movies" :key="movie.id" class="col-4 col-xl-3 card align-items-center">

            <h4>{{movie.title}}</h4>
            <div>{{movie.original_title}}</div>
            <!-- <img 
            v-if=" movie.original_language !== 'en' "
            :src="takeFlagLang(movie.original_language)"
            :alt="flag" 
            class="d-block"
            > -->
            <div> {{movie.original_language}} </div>
            <div>{{movie.vote_average}}</div>
            
        </div>
    </div>
</template>

<script>

/*

adult: false
backdrop_path: "/xENKhotB6aYBlnDH2lE0m2y22v1.jpg"
genre_ids: Array(1)
id: 565028
original_language: "en"
original_title: "Candyman"
overview: "Per quanto possano ricordare, i residenti del quartiere popolare di Chicago Cabrini Green, sono sempre stati terrorizzati dal passaparola di una storia spettrale su un killer sovrannaturale con un uncino al posto di una mano che può essere facilmente evocato da chi ha l’ardire di ripetere cinque volte il suo nome davanti a uno specchio. Ai nostri giorni, dieci anni dopo la demolizione dell’ultima Cabrini tower, l’artista visuale Anthony McCoy (Yahya Abdul-Mateen II) e la sua ragazza, la direttrice di una galleria d’arte Brianna Cartwright (Teyonah Parris), si trasferiscono in un condominio di lusso del Cabrini, che nel frattempo si è gentrificato tanto da essere divenuto irriconoscibile e abitato da rampanti millennial."
popularity: 77.169
poster_path: "/qZzWBsUDxsjHvh1Rpy6AOIzYjcI.jpg"
release_date: "2021-08-25"
title: "Candyman"
video: false
vote_average: 6.2
vote_count: 848
*/

export default {

  name: "FilmList",

  props: {
    movies: Array
  },
  
  methods: {
    takeFlagLang(lang) {
        return "https://www.kidlink.org/icons/f0-"+ lang +".gif "
      }
  },

  computed: {
      
  }

}

</script>

<style lang="scss" scoped>
    img {
      width:20px;
    }
</style>