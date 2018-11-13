<template lang="html">
<div class="container">
    <header>
        
 <nuxt-link to="/">Regresar</nuxt-link>
 <h1 class='title'>{{album.title}}</h1>
    </header>

     <div class="columns is-multiline">
       <div class="column is-one-quarter"  v-for="photo in photos" :key="photo.id">
           <img :src="photo.url" :alt="photo.title" />
       </div>

     </div>
</div>
   
</template>
<script>
import env from "../../config/env";
import axios from "axios";
import router from 'vue-router';
export default {
    name:'AlbumIndvPage',
    data(){
        return {
            album: {},
            photos: [],
        }
    },
created: async function() {
  let albumResponse = await axios.get(`${env.endpoint}/albums/${this.$route.params.id}`);
   this.album = albumResponse.data;
  let photosResponse = await    axios.get(`${env.endpoint}/albums/${this.$route.params.id}/photos`);
   this.photos = photosResponse.data;
}
    
}
</script>
<style scoped>
.container {
    text-align: center;
}
header {
    margin-top: 100px;
    margin-bottom: 100px;
}

</style>
