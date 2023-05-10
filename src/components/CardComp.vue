<script>
  export default{
    name: 'CardComp',
    props: ['infoFilm']
  }


</script>

<template>

<div class="col-12 col-md-6 col-lg-3 mb-5">
  <div class="card">
    <img src="..." class="card-img-top" :alt="infoFilm.original_title">
    <div class="card-body">
      <h5 class="card-title">{{ infoFilm.original_title }}</h5>
      <p class="card-text">{{ infoFilm.overview }}</p>
    </div>
  </div>
</div>

</template>

<style lang="scss" scoped>

</style>