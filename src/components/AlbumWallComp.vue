<template>
  <div class="container">
    <LoaderComp :class="(albumArr.length == 10)? 'd-none' : ''"/>
    <div v-if="albumArr.length == 10" class="container__cards">
      <AlbumComp v-for="(elm, i) in albumArr" :key="i"
        :image="elm.poster"
        :artist="elm.author"
        :title="elm.title"
        :year="elm.year"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import AlbumComp from "./partials/AlbumComp.vue"
import LoaderComp from "./LoaderComp.vue"

export default {
name: 'AlbumWallComp',
components : {
  AlbumComp,
  LoaderComp
},
data(){
  return{
    albumArr : []
  }
},
created(){
  axios.get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        console.log('PROVA:', res.data.response);
        this.albumArr = res.data.response
      })
      .catch((error) => {
        console.log(error)
      })
},
}
</script>

<style scoped lang='scss'>
.d-none{display: none;}
.container{
  width: 70%;
  margin: 0 auto;
  height: 92vh;
  overflow-y: auto;
  &__cards{
    display: flex;
    flex-wrap: wrap;
  }
}
</style>