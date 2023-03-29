<script>
import CardItem from "./CardItem.vue";

import axios from "axios";

import { store } from "../store.js";

export default {

    name: "AppMain",

    data() {

        return {

            store,

        }
    },

    components: {

        CardItem,

    },

    created() {

        axios.get(this.store.APIcall).then((res) => {
            console.log(res);
            console.log(res.data.data);

            this.store.cards = res.data.data;
        });

        // axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0').then((res) => {
        //     console.log(res);
        //     console.log(res.data.data);

        //     this.store.cards = res.data.data;


        // });

    },

};
</script>


<template>
    <main>
        <h1>I wish it were Magic The Gathering</h1>
        <div class="content">
            <CardItem v-for="(item, index) in store.cards" :card="item"></CardItem>

        </div>

    </main>
</template>
  
<style lang="scss" scoped>
h1 {
    padding: 20px 0;
    margin: auto;
    text-align: center;
}

.content {
    max-width: 1200px;
    margin: auto;

    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    gap: 20px;
}
</style>