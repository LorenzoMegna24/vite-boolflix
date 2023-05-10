<script>
  export default{
    name: 'CardComp',
    props: ['infoFilm', 'infoSerie'],
    data(){
      return{
        stato: '',
        imgBandiera: 'https://flagsapi.com/state/flat/64.png'
      }
    },
  methods:{
    bandiera(infoFilm){
       return this.imgBandiera.replace('state', infoFilm.original_language.toUpperCase());
      }
  }
  }
  


</script>

<template>

<div class="col-12 col-md-6 col-lg-3 mb-5">
  <div class="card">
    <img src="..." class="card-img-top" :alt="infoFilm.original_title">
    <div class="card-body">
      <h5 class="card-title">{{ infoFilm.original_title }}</h5>
      <p class="card-text">{{ infoFilm.overview }}</p>
      <div>
        <img :src="bandiera(infoFilm)" :alt="infoFilm.original_language">
      </div>
    </div>
  </div>
    <div class="col-12 col-md-6 col-lg-3 mb-5">
    <div class="card">
      <img src="..." class="card-img-top" :alt="infoSerie.original_name">
      <div class="card-body">
        <h5 class="card-title">{{ infoSerie.original_name }}</h5>
        <p class="card-text">{{ infoSerie.overview }}</p>
        <div>
          <!-- <img :src="bandiera(infoFilm)" :alt="infoFilm.original_language"> -->
        </div>
      </div>
    </div>
  </div>
</div>

</template>

<style lang="scss" scoped>

</style>