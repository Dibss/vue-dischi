<template>
  <div class="searchContainer">
    <form action="">
      <select name="genre-artist" id="select" v-model="select">
        <option :value="genre" v-for="genre in genArr" :key="genre.id">{{genre}}</option>
        <option :value="artist" v-for="artist in artArr" :key="artist.id">{{artist}}</option>
      </select>
      <button @click.prevent="$emit('search', select)" @click="inputSearch()">Cerca</button>
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
    select: "",
  }
},
methods : {
  inputSearch : function(){
    let a = document.getElementById("select").value;
    console.log(a);
  }
},
}
</script>

<style scoped lang='scss'>
.searchContainer{
  width: 98.5%;
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