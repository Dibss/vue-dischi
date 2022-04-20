<template>
  <div id="app">
    <header>
      <HeaderComp></HeaderComp>
    </header>
  </div>
</template>

<script>
import HeaderComp from "../src/components/HeaderComp.vue"

export default {
  name: 'App',
  components: {
    HeaderComp,

  }
}
</script>

<style lang="scss">
*{padding: 0; margin: 0; box-sizing: border-box;}
#app{
  width: 100vw;
  height: 100vh;
  background-color: #1e2d3b;
}
</style>

// Create un nuovo progetto utilizzando Vue CLI e definite i componenti necessari per strutturare il layout come da screenshot allegato.
// Al caricamento della pagina, effettuate una chiama ajax all'API di boolean:
// https://flynn.boolean.careers/exercises/api/array/music
// e con i dati restituiti, stampate una card per ogni disco musicale.
// Bonus:
// Creare un componente loader da visualizzare fintantoché i risultati non sono pronti.
