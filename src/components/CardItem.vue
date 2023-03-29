<script>

export default {

    name: "CardItem",

    data() {

        return {

        }

    },


    props: {

        card: Object,

    },

}

</script>

<template>
    <div class="card">

        <img :src="card.card_images[0].image_url" alt="card image">

        <div class="title">

            {{ card.name }}

        </div>

    </div>
</template>

<style lang="scss" scoped>
.card {
    font-weight: bold;
    color: #3f3f3f;
    text-shadow: 0 0 10px #d4af37, 0 0 20px #d4af37, 0 0 30px #9370db, 0 0 40px #9370db;

    border: 1px solid black;
    padding: 0px;
    width: 200px;
    text-align: center;
    background-image: linear-gradient(to right, #b0b0b0 0%, #e0e0e0 50%, #b0b0b0 100%);
}

img {
    width: 100%;
    height: auto;
}
</style>

