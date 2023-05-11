<script>
   import { store } from '../store'
   import CardComp from './CardComp.vue';
  export default{
    name: 'ResultsComp',
    components: {
      CardComp,
    },
    data(){
      return{
        store
      }
    }

  }


</script>

<template>

  <div class="container mt-5">
    <div class="row" v-if="store.arrayFilm.length">
      <h2 class="mb-5">Film</h2>
      <CardComp  v-for="(film, index) in store.arrayFilm" :key="index" :info="film"/>
    </div>
    <div class="row" v-if="store.arraySeries.length">
      <h2 class="mb-5">Serie TV</h2>
      <CardComp v-for="(serie, index) in store.arraySeries" :key="index" :info="serie"/>
    </div>
  </div>

</template>

<style lang="scss" scoped>

</style>