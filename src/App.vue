<script >
  import axios from 'axios';
  import { store } from './store'
  import HeaderComp from './components/HeaderComp.vue';

  export default{
    name: 'App',
    components: {
      HeaderComp,
    },
    data(){
      return{
        store
      }
    },
    created() {

    },
    computed:{

    },
    methods:{
      cercaFilm(){
        axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${store.apiKey}&query=${store.ricercaTitolo}`).then( (res)=>{
          store.arrayRisultati = res.data.results
        })
      }
    }
  }
</script>

<template>
  <HeaderComp @callApi="cercaFilm()"/>
</template>

<style lang="scss">
@use './style/main.scss';
</style>
