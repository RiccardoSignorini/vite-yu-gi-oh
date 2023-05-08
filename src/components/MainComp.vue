<script>
  import CardsComp from "./CardsComp.vue"

  export default{
    name: "MainComp",
    components: {
      CardsComp
    }
  }
</script>

<template>
  <div id="main">
    <select name="" id="">Da fare dopo</select>
    <div>
      <div>
        <h5>Found ... cards</h5>
      </div>
      <div id="cards">
        <CardsComp/>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
  #main{
    background-color: rgb(213, 141, 64);
  }
</style>