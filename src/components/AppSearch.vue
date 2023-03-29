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

<style lang="scss" scoped></style>
