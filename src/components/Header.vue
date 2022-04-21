<template>
    <header>
        <div class="searchBar">
            <!-- inserting here the user text -->
            <input type="text" placeholder="search" v-model="TextToSearch">
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

<style>

</style>