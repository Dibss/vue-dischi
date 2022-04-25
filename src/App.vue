<template>
  <div id="app">
    <header>
      <HeaderComp/>
    </header>
    <main>
      <AlbumWallComp/>
    </main>
  </div>
</template>

<script>
import HeaderComp from "../src/components/HeaderComp.vue"
import AlbumWallComp from "../src/components/AlbumWallComp.vue"

export default {
  name: 'App',
  components: {
    HeaderComp,
    AlbumWallComp
  }
}
</script>

<style lang="scss">
*{padding: 0; margin: 0; box-sizing: border-box;}
#app{
  width: 100%;
  height: 100vh;
  background-color: #1e2d3b;
  font-family: sans-serif;
}
main{
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>

// Descrizione:
// Continuate a lavorare nella stessa repo di ieri e aggiungete una select per filtrare i dischi in base al genere: quando l'utente seleziona un genere dalla lista, vengono visualizzati solamente i dischi con il genere corrispondente.
// Bonus:
// Aggiungere un ulteriore select che filtra gli album per artista.
