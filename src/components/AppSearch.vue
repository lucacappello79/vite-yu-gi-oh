<script>

import { store } from "../store.js";

export default {

    name: "AppSearch",

    data() {

        return {
            store,
        }
    },
}

</script>

<template>
    <div class="search">
        <input v-model="store.cardName" type="text" placeholder="Search card name" @keyup.enter="$emit('searchCardName')">
        <button @click="$emit('searchCardName')">Search</button>
    </div>
</template>

<style lang="scss" scoped>
.search {
    text-align: center;
    padding: 20px 0 50px;

    input {
        margin-right: 20px;
    }
}
</style>
