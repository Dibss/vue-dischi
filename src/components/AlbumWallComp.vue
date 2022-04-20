<template>
  <div>
  </div>
</template>

<script>
export default {
name: 'AlbumWallComp',
data(){
  return{
    albumArr : []
  }
},
created(){
  axios.get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res)=>{
        console.log(res.data);
        this.albumArr = res.data
      })
      .catch((error)=>{
        console.log(error)
      })
}
}
</script>

<style scoped lang='scss'>
</style>