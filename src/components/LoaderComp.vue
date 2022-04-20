<template>
  <div>
    <h2>Aspetta che carica perché hai internet lento &#128128;</h2>
  </div>
</template>

<script>
export default {
name: 'LoaderComp',
}
</script>

<style scoped lang='scss'>
div{
  display: flex;
  justify-content: center;
  align-items: center;
  height: 75vh;
  h2{
    color: #fff;
    font-size: 2rem;
  }
}
</style>