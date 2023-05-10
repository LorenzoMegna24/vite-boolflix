<script>
  export default{
    name: 'CardSerieComp',
    props: ['infoSerie'],
  
  }
  


</script>

<template>

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

</template>

<style lang="scss" scoped>

</style>