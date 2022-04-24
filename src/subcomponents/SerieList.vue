<template>
  <div class="row w-75 m-auto d-flex">
        <h2>SERIE</h2>
        <div v-for="serie in series" :key="serie.id" class="col-4 col-xl-3 card-rf ">
            <img :src="takeImgPoster(serie.poster_path)" class="img-fluid" />
            <div class="text-post-rf">
                <h5>{{serie.name}}</h5>
                <div>{{serie.original_name}}</div>
                <div> {{serie.original_language}} </div>
                <div>
                    <span>Voto: </span>
                    <i v-for="(m,index) in takeVote(serie.vote_average)" :key="index" class="fa-solid fa-star">
                    </i>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

/*
backdrop_path: "/rrBtfYvuTAR2BsCVgl31LVSenRh.jpg"
first_air_date: "2011-07-01"
genre_ids: Array(4)
id: 43270
name: "Blood-C"
origin_country: Array(1)
original_language: "ja"
original_name: "Blood-C"
overview: "Blood-C si concentra su Saya Kisaragi, una ragazza apparentemente normale che funge da fanciulla del santuario in una città di campagna; in realtà, è un'abile spadaccina incaricata dal padre di sconfiggere l'anziano Bairns, mostri che si nutrono di sangue umano. Man mano che le sue battaglie diventano più disperate e più persone a cui tiene cadono vittima degli Elder Bairns, Saya inizia a trovare difetti nella sua realtà e alla fine scopre una verità inquietante su se stessa, la città e i suoi amici sopravvissuti."
popularity: 28.386
poster_path: "/5Mn9uQf5mqZ4ZqsZoi7oCcQslUj.jpg"
vote_average: 8.1
vote_count: 135
*/

export default {
  name: "SerieList",
  props: {
    series: Array,
  },
  methods: {
    takeImgPoster(lastUrl){
          return "https://image.tmdb.org/t/p/original" + lastUrl ;
    },
    takeVote(vote){
      // console.log(Math.round(7.2 / 2));
      const newVote = Math.round(vote / 2);
      console.log(newVote);
      return newVote;
    }
  }
}
</script>

<style lang="scss" scoped>
   .row {
      color: white;
      h2 {
        color: black;
      }
    }
    .card-rf:hover{
      background-color: black;
      img {
        display:none;
      }
      .text-post-rf {
        display: block;
      }
    }
    
    .text-post-rf {
      display:none;
    }
</style>