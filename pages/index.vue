<template lang="html">
<div class="container">
<h1 class="title">albums de la página  </h1>
  <div class="columns is-multiline">
   <AlbumCard :album="album" v-for="album in albuns" :key="album.id"/>
  </div>
</div>

</template>
<script>


import env from "../config/env";
import axios from "axios";
import  AlbumCard from '../components/AlbumCard';

export default {
  name: "IndexPage",
  components: {
      AlbumCard
  },
  data(){
      return {
         albuns: [] 
      }
  },
  created: async function() {
let response  = await  axios.get(`${env.endpoint}/albums/`);
     this.albuns= response.data;
}
}
</script>
<style scoped>
</style>