<template>
  <div class="searchContainer">
    <form action="">
      <select name="genre" id="selectGenre" v-model="selectGenre">
        <option :value="genre" v-for="genre in genArr" :key="genre.id">{{genre}}</option>
      </select>
      <button @click.prevent="$emit('searchGenre', selectGenre)">Cerca</button>
      <select name="artist" id="selectArtist" v-model="selectArtist">
        <option :value="artist" v-for="artist in artArr" :key="artist.id">{{artist}}</option>
      </select>
      <button @click.prevent="$emit('searchArtist', selectArtist)">Cerca</button>
    </form>
  </div>
</template>

<script>
export default {
name: 'SearchComp',
props : {
  genArr : Array,
  artArr : Array,
},
data(){
  return{
    selectGenre : "",
    selectArtist : ""
  }
}
}
</script>

<style scoped lang='scss'>
.searchContainer{
  width: 98%;
  text-align: right;
  margin-top: 1em;
  select{
    padding: 0.3em;
    margin-left: 0.5em;
  }
  button{
    margin-left: 1em;
    padding: 0.3em;
  }
}
</style>