<template>
  <div id="app">
      <Header @text="searchtext"/>
      <Main :movies="movies" :series="series"/>
  </div>
</template>

<script>

// import axios
import axios from 'axios';

// import apikey 
import {api} from "./apikey.js"
// oppure posso fare cosi import api from "./apikey.js" e nel js dovra' esserci..


// import components
import Header from "@/components/Header.vue"
import Main  from "@/components/Main.vue"


export default {
  name: 'App',

  // datas
  data(){

      return {
        // with this var we don't ask twice for a call API
        searching: false,

        // we need some datas to do the request data from the API that we will send to main
        apiUrl: "https://api.themoviedb.org/3/search/",
        apiKey: api,
          // query is a var with word filter to search the films/series
        query:"",

        // here movies and series will contain the datas of the movies and series
        movies:[],
        series:[],
      }
  },

  // components
  components: {
    Header,
    Main
  },

  // methods, where are functions
  methods: {

      // here a take the word filter from the input box of the header and call the metho queryMovies
      searchtext(inputText) {
          this.query = inputText;
          this.queryMovies();
          this.queryTV();

      },

      //this method take the movie data and insert them in the var movies
      queryMovies(){
          if (!this.searching && this.query.length > 0){
            // console.log("ciao")
              // setting searching to true so we can't ask for another api once aske one
              this.searching = true;

              this.queryApi("movie").then((response)=>{
                  console.log("movies",response)
                  //here the var movie take the datas movies from the API
                  this.movies = response.data.results

                  // console.log("my movies", this.movies)
              });
          }
      },

      // this method take series data
      queryTV(){
        
        this.searching = false;
        
        if (!this.searching && this.query.length > 0){
            // console.log("ciao")
              // setting searching to true so we can't ask for another api once aske one
              this.searching = true;

              this.queryApi("tv").then((response)=>{
                  console.log("series",response)
                  //here the var movie take the datas movies from the API
                  this.series = response.data.results
              });
          }
      },

      // these method call the API if the query length is at least 1 and if we are not searching
      queryApi(genre){
            // paramaters that we must insert in the request call API
            const params = {
                query: this.query,
                api_key: this.apiKey,
                language: "it-IT"
            }
            // call API
           return axios.get(this.apiUrl + genre, {params}).catch(error=>{
              console.log(error);
              this.searching = false;
            })
          
      },
  },
  
}
</script>

<style lang="scss" >


// import bootstrap
@import "~bootstrap/scss/bootstrap";

  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

</style>
