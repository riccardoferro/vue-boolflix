<template>
    <header>
        <h1>
          BOOLFLIX
        </h1>
        <div class="searchBar">
            <!-- inserting here the user text -->
            <input type="text" placeholder="search for a movie" v-model="TextToSearch">
            <!-- sent the user text to the components APP -->
            <button @click="$emit('text',TextToSearch)"> Search </button>
        </div>
    </header>
</template>

<script>
export default {

  name:"HeaderComponent",
  
  // variables
  data(){
      return{
        TextToSearch: ""
      };
  }
}

</script>

<style lang="scss" scoped>
  header {
    background-color: black;
    display: flex;
    justify-content: space-between;
    align-items: center;
    h1 {
      color: red;
    }
    .searchBar {
        margin-right: 10px;
        button {
          margin-left: 10px;
        }
    }
  }
</style>