<script >
  import axios from 'axios';
  import { store } from './store'
  import HeaderComp from './components/HeaderComp.vue';
  import ResultsComp from './components/ResultsComp.vue'

  export default{
    name: 'App',
    components: {
      HeaderComp,
      ResultsComp,
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
        axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${store.apiKey}&language=it_IT&query=${store.ricercaTitolo}`).then( (res)=>{
          console.log(res.data.results);
          store.arrayFilm = res.data.results;
          axios.get(`https://api.themoviedb.org/3/search/tv?api_key=${store.apiKey}&language=it_IT&query=${store.ricercaTitolo}`).then((res)=>{
            console.log(res.data.results);
            store.arraySeries = res.data.results
          })
        })
      }
    }
  }
</script>

<template>
  <HeaderComp @callApi="cercaFilm()"/>
  <ResultsComp/>
</template>

<style lang="scss">
@use './style/main.scss';
</style>
