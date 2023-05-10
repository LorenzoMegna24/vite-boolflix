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
    <div class="row">
      <CardComp  v-for="(element, index) in store.arrayFilm" :key="index" :infoFilm="element"/>
      <CardComp v-for="(element, index) in store.arraySeries" :key="index" :infoSerie="element"/>
    </div>
  </div>

</template>

<style lang="scss" scoped>

</style>