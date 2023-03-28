<script>
import { store } from "../store.js";
import axios from "axios";
import CardItem from "./CardItem.vue";

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

        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0').then((res) => {
            console.log(res);
            console.log(res.data.data);

            this.store.cards = res.data.data;

        });

    },

};
</script>


<template>
    <main>
        <div class="content">
            <CardItem v-for="(item, index) in store.cards" :card="item"></CardItem>
        </div>

    </main>
</template>
  
<style lang="scss" scoped>
.content {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    gap: 20px;
}
</style>