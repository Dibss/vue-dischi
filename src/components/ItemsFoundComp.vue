<template>
  <div class="foundContainer">
    <span>Found {{numItems}} albums</span>
  </div>
</template>

<script>
export default {
name: 'ItemsFoundComp',
props : {
  numItems : Number
}
}
</script>

<style scoped lang='scss'>
.foundContainer{
  text-align: center;
  margin-top: 1em;
  span{
    color: #fff;
  }
}
</style>