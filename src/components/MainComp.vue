<script>
  import CardsComp from "./CardsComp.vue"
  import FilterCardsComp from "./FilterCardsComp.vue"
  import {store} from "../store"
  import axios from "axios"
  

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
    },
    created(){
      this.callApiCards();
    },
    methods: {
      // CHIAMATA API CARTE
      callApiCards(){

        // if(store.arrayArchetype !== ''){
        //   axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${encodeURIComponent(store.arrayArchetype)}`).then((res)=>{
        //     this.store.arrayCards = res.data.data
        //   })  
        // } else{
        //   axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=52&offset=0").then((res)=>{
        //     this.store.arrayCards = res.data.data
        //   })
        // }

        axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=52&offset=0").then((res)=>{
            this.store.arrayCards = res.data.data
          })
        
      }
    }
  }
</script>

<template>
  <div id="main" class="p-3">
    <div class="container">

      <!-- RICERCA PER ARCHETIPI -->
      <FilterCardsComp @changeArchetype="callApiCards()"/>
      
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