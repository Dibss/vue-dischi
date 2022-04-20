<template>
  <div class="card">
    <div>
      <img :src="image" :alt="title + 'album image'">
    </div>
    <h2>{{title}}</h2>
    <div>
      <span class="d-block">{{artist}}</span>
      <span>{{year}}</span>
    </div>
  </div>
</template>

<script>

export default {
name: 'AlbumComp',
props : {
  image : String,
  title : String,
  artist : String,
  year : String,
}
}
</script>

<style scoped lang='scss'>
.d-block{display: block;}
.card{
  background-color: #2e3a46;
  width: calc(100% / 5);
  img{
    max-width: 100%;
    height: auto;
  }
}
</style>