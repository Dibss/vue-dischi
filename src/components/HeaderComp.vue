<template>
  <div class="container">
    <img src="../assets/img/logo-small.svg" alt="spotify logo">
  </div>
</template>

<script>
export default {
  name: "HeaderComp",
}
</script>

<style scoped lang='scss'>
.container{
  background-color: #2e3a46;
  height: 8vh;
  display: flex;
  justify-content: space-between;
  align-items: center;
  img{
    width: 3%;
    height: auto;
    padding: 1em 0 1em 1em;
  }
}
</style>