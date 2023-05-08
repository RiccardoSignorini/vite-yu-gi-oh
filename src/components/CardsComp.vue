<script>
    export default{
        name: "CardsComp",
        props: ["cardDates"]
    }
</script>

<template>
    <div class="card my-2">
        <img :src="cardDates.card_images[0].image_url" alt="" class="card-img-top">
        <div class="card-body text-center align-items-center">
            <h5 class="card-title">{{cardDates.name}}</h5>
            <p class="card-text">{{cardDates.archetype}}</p>
            <p class="card-text">({{cardDates.frameType}})</p>
        </div>
    </div>
</template>

<style scoped lang="scss">
    .card{
        background-color: rgb(213, 141, 64);

        .card-body{
            height: 150px;
        }
    }
</style>