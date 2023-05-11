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
    bandiera(x){
       
       if (x == 'en') {
        x = 'gb'
        return this.imgBandiera.replace('state', x.toUpperCase());
       }else{
        return this.imgBandiera.replace('state', x.toUpperCase());
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
    },
    voto(){
      return Math.ceil( this.info.vote_average / 2 )
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
      <img class="bandiera" :src="bandiera(info.original_language)" :alt="info.original_language">
      <div>
        <i v-for="n in 5" class="fa-star" :class="( n <= voto() ) ? 'fa-solid' : 'fa-regular'"></i>
      </div>
    </div>
  </div>
</div>

</template>

<style lang="scss" scoped>
.bandiera{
  width: 25px;
}

i{
  color: rgb(237, 178, 0);
}
</style>