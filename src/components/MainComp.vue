<script>
  import CardsComp from "./CardsComp.vue"
  import FilterCardsComp from "./FilterCardsComp.vue"
  import {store} from "../store"
  

  export default{
    name: "MainComp",
    components: {
      CardsComp,
      FilterCardsComp
    },
    data(){
      return{
        store
      }
    }
  }
</script>

<template>
  <div id="main" class="p-3">
    <div class="container">

      <FilterCardsComp/>
      
      <!-- NUM RISULTATO RICERCA -->
      <div id="search-results" class="text-light p-3">
        <h5>Found ... cards</h5>
      </div>

      <!-- CICLO CARD SINGOLA DA COMPONENTE -->
      <div id="cards" class="container p-4">
        <div class="row">
          <div class="col-3" v-for="(elem,index) in store.arrayCards" :key="index">
            <CardsComp :cardDates="elem"/>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
  #main{
    background-color: rgb(213, 141, 64);

    #search-results{
      background-color: rgb(33, 37, 41);
    }

    #cards{
      background-color: white;
    }
  }
</style>