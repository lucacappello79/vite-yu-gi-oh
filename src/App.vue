<script>
import axios from "axios";
import { store } from "./store.js"

import AppMain from "./components/AppMain.vue"
// import AppSearch from "./components/AppSearch.vue"

export default {
  data() {
    return {
      store,
    };
  },

  components: {
    AppMain,
    // AppSearch
  },

  created() {

    axios.get(this.store.APIcall).then((res) => {
      console.log(res);
      console.log(res.data.data);
      this.store.cards = res.data.data;
    });
  },

  methods: {

    search() {

      let apiNewString = this.store.APIquery + this.store.cardName;

      axios.get(apiNewString).then((res) => {
        this.store.cards = res.data.data;
      });

    },

  },

};
</script>


<template>
  <div class="container">

    <!-- <AppSearch @searchCardName="search"></AppSearch> -->
    <AppMain :search="search"></AppMain>

  </div>
</template>


<style lang="scss"></style>
