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
<div class="contenitore bg-dark">
  <div class="container bg-dark">
    <div class="row" v-if="store.arrayFilm.length">
      <h2 class="mb-5 mt-5 text-danger">Film</h2>
      <CardComp  v-for="(film, index) in store.arrayFilm" :key="index" :info="film"/>
    </div>
    <div class="row" v-if="store.arraySeries.length">
      <h2 class="mb-5 text-danger">Serie TV</h2>
      <CardComp v-for="(serie, index) in store.arraySeries" :key="index" :info="serie"/>
    </div>
  </div>
</div>

</template>

<style lang="scss" scoped>
.contenitore{
  height: 88%;
  overflow: auto;
}


</style>