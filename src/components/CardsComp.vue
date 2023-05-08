<script>
    import {store} from "../store"

    export default{
        name: "CardsComp",
        data(){
            return{
                store
            }
        }
    }
</script>

<template>
    <div class="card">
        <img src="" alt="" class="card-img-top">
        <div class="card-body text-center">
            <h5 class="card-title">Name Card</h5>
            <span class="card-text">Archetype</span>
        </div>
    </div>
</template>

<style scoped lang="scss">

</style>