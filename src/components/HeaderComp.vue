<script >
  import { store } from '../store'
  export default{
    name: 'HeaderComp',
    data(){
      return{
        store
      }
    }

  }
</script>

<template>
  <div class="bg-black p-3 d-flex align-items-center justify-content-between">
    <h1 class="text-danger me-5">BOOLFLIX</h1>
    <div class="input-group w-50">
      <input type="text" class="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-default" 
      v-model="store.ricercaTitolo">
      <button class="input-group-text" id="inputGroup-sizing-default" @click="$emit('callApi')">Search</button>
    </div>
  </div>
</template>

<style lang="scss" scoped>

</style>
