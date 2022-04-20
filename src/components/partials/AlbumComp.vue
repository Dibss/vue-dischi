<template>
  <div class="card">
    <div class="card__img">
      <img :src="image" :alt="title + 'album image'">
    </div>
    <div class="card__details">
      <h2>{{title}}</h2>
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
  width: calc(100% / 5 - 2em);
  margin: 1em;
  text-align: center;
  padding: 1em 0;
  &__img{
  margin-bottom: 1em;
  img{
    max-width: 80%;
    height: auto;
  }
  }
  &__details{
    h2{
      color: #fff;
      font-size: 1.2rem;
      text-transform: uppercase;
      width: 90%;
      margin: 0 auto 1em;
    }
    span{
      color: #7a7e79;
      font-size: 1.1rem;
    }
  }
}
</style>