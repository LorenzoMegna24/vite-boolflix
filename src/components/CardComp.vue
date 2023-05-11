<script>
  export default{
    name: 'CardComp',
    props: ['info'],
    data(){
      return{
        imgBandiera: 'https://flagsapi.com/state/flat/64.png'
      }
    },
  methods:{
    bandiera(info){
       
       if (this.info.original_language == 'en') {
        this.info.original_language = 'gb'
        return this.imgBandiera.replace('state', this.info.original_language.toUpperCase());
       }else{
        return this.imgBandiera.replace('state', this.info.original_language.toUpperCase());
       }
      },

    titolo(){
      if(this.info.original_title){
        return this.info.original_title
      }else {
        return this.info.original_name
      }
    },
    thumb(){
      if (this.info.poster_path) {
        return `https://image.tmdb.org/t/p/w500/${this.info.poster_path}`
      }else if (this.info.poster_path == null) {
        return '/img/errore-404.jpg'
      }
    }
  }
  }
  


</script>

<template>

<div class="col-12 col-md-6 col-lg-3 mb-5">
  <div class="card">
    <img :src="thumb()" class="card-img-top" :alt="titolo()">
    <div class="card-body">
      <h5 class="card-title">{{ titolo() }}</h5>
      <p class="card-text">{{ info.overview }}</p>
      <div>
        <img :src="bandiera(info)" :alt="info.original_language">
      </div>
    </div>
  </div>
</div>

</template>

<style lang="scss" scoped>

</style>