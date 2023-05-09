<script>
    import {store} from "../store"
    import axios from 'axios'

    export default{
        name: "FilterCardsComp",
        data(){
        return{
            store
        }
        },
        created(){
        this.callApiArchetype();
        },
        methods: {
            // CHIAMATA API ARCHETIPO
            callApiArchetype(){
            axios.get("https://db.ygoprodeck.com/api/v7/archetypes.php").then((res)=>{
                console.log(res.data)
                this.store.arrayArchetype = res.data
            })
            }
        }
    }
</script>

<template>
    <!-- RICERCA PER ARCHETIPI -->
    <select name="Archetype" id="archetype" class="my-4" v-model="store.valueArchetype">
        <option :value="elem.archetype_name" v-for="(elem,index) in store.arrayArchetype" :key="index">{{ elem.archetype_name }}</option>
    </select>
</template>

<style scoped lang="scss">

</style>