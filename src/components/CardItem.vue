<script>
import { store } from "../store.js";
export default {

    name: "CardItem",

    data() {

        return {

            store,

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
    border: 1px solid black;
    padding: 10px;
    width: 200px;
    text-align: center;
}

img {
    width: 100%;
    height: auto;
}
</style>

