<template lang="html">
     <div class=" column is-one-quarter">
         <div class="box">
         <h1>{{album.title}}</h1>
        <nuxt-link :to="`/albums/${album.id}`" class="button  is-primary" >ver album</nuxt-link>
         </div>
        </div>
</template>

<script>
export default {
    name: 'AlbumCard',
props: {
    album: Object
}
}
</script>
<style   lang="css">
.box {
    padding: 1em;
}
h3{
    min-height: 5em;
}
</style>



