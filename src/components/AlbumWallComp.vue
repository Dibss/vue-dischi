<template>
  <div id="main-container">
    <SearchComp @search="filteredGenre" @searchArtist="filteredArtist" :genArr="genreArr" :artArr="artistsArr"/>
    <div class="container"> 
      <LoaderComp :class="(albumArr.length == 10)? 'd-none' : ''"/>
      <div v-if="albumArr.length == 10" class="container__cards">
        <AlbumComp v-for="album in filtered()" :key="album.id"
          :image="album.poster"
          :artist="album.author"
          :title="album.title"
          :year="album.year"
        />
      </div>
      <ItemsFoundComp :numItems="filtered().length"/>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import AlbumComp from "./partials/AlbumComp.vue"
import LoaderComp from "./LoaderComp.vue"
import ItemsFoundComp from "./ItemsFoundComp.vue";
import SearchComp from "./SearchComp.vue";

export default {
name: 'AlbumWallComp',
components : {
    AlbumComp,
    LoaderComp,
    ItemsFoundComp,
    SearchComp
},
data(){
  return{
    albumArr : [],
    genreArr : [],
    artistsArr : [],
    select : "",
    selectArt : ""
  }
},
created(){
  this.getAlbums();
  this.getGenres();
  this.getArtists();
},
methods : {
  getAlbums(){
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        console.log('ALBUM:', res.data.response);
        this.albumArr = res.data.response
      })
      .catch((error) => {
        console.log(error)
      });
  },
  getGenres(){
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        for(let i = 0; i < res.data.response.length; i++){
          if(this.genreArr.includes(res.data.response[i].genre)){
            this.genreArr
          } else {
            this.genreArr.push(res.data.response[i].genre)
          }
        }
        console.log("GENERI", this.genreArr)
      })
      .catch((error) => {
        console.log(error)
      })
  },
  getArtists(){
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        for(let i = 0; i < res.data.response.length; i++){
          if(this.artistsArr.includes(res.data.response[i].author)){
            this.artistsArr
          } else {
            this.artistsArr.push(res.data.response[i].author)
          }
        }
        console.log("ARTISTI", this.artistsArr)
      })
      .catch((error) => {
        console.log(error)
      })
  },

  filteredGenre(selected){
    this.select = selected;
    console.log(this.select);
  },

  filteredArtist(selected){
    this.selectArt = selected;
    console.log(this.selectArt);

  },

  filtered(){
    if(this.select == "" && this.selectArt == ""){
      return this.albumArr
    } else {
      return this.albumArr.filter( (elem) => {
        return elem.author.includes(this.selectArt) && elem.genre.includes(this.select)
      })
    }
  },
}
}
</script>

<style scoped lang='scss'>
.d-none{display: none;}
#main-container{
  overflow-y: auto;
  .container{
    width: 70%;
    margin: 0 auto;
    height: 80vh;
    &__cards{
      display: flex;
      flex-wrap: wrap;
    }
  }
}
</style>