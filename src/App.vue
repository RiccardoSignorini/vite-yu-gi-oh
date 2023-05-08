<script>
  import HeaderComp from "./components/HeaderComp.vue"
  import MainComp from "./components/MainComp.vue"

  import {store} from "./store"

  export default{
    name: "App",
    data(){
      return{
        store
      }
    },
    components: {
      HeaderComp,
      MainComp
    },
    created(){
      // callApi();
    },
    methods: {
      callApi(){
        axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=30&offset=0").then((res)=>{
          console.log(res.data.data)
        })
      }
    }
  }
</script>

<template>
  <HeaderComp/>
  <MainComp/>
</template>

<style lang="scss">

</style>
