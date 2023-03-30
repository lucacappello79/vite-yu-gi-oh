<script>
import { store } from "../store.js";

import CardItem from "./CardItem.vue";
import AppSearch from "./AppSearch.vue";

export default {

    name: "AppMain",

    data() {

        return {

            store,

        }
    },

    components: {

        AppSearch,
        CardItem,

    },

    props: {

        search: Function,

    }



};
</script>


<template>
    <main>

        <h1>I wish it were Magic The Gathering</h1>

        <AppSearch @searchCardName="search"></AppSearch>

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