<script>
  import CardsComp from "./CardsComp.vue"
  import {store} from "../store"
  

  export default{
    name: "MainComp",
    components: {
      CardsComp,
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
      <select name="" id="">Da fare dopo</select>
      <div>
        <h5>Found ... cards</h5>
      </div>
      <div id="cards" class="container p-3">
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
    #cards{
      background-color: white;
    }
  }
</style>