<script>
import { store } from "./store.js"
import AppMain from "./components/AppMain.vue"
import AppSearch from "./components/AppSearch.vue"
import axios from "axios";


export default {
  data() {
    return {

      store,

    };
  },

  components: {
    AppMain,
    AppSearch
  },

  methods: {

    search() {
      // let apiNewString = this.store.APIcall + this.store.APIquery + this.store.cardName
      let apiNewString = this.store.APIquery + this.store.cardName;

      axios.get(apiNewString).then((res) => {
        console.log(res.data.data);

        this.store.cards = res.data.data;

      });
    },
  },

};
</script>


<template>
  <div class="container">

    <AppSearch @searchCardName="search"></AppSearch>
    <AppMain></AppMain>

  </div>
</template>


<style lang="scss">
.container {

  background-color: orange;
}
</style>
