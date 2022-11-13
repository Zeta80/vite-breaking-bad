<script >
import axios from "axios";
import { store } from "./store";
import AppHeader from './components/AppHeader.vue';
import CharactersList from './components/CharacterList.vue';
import AppLoader from "./components/AppLoading.vue";


export default {
  components: {
    AppHeader,
    CharactersList,
    AppLoader
  },

  data() {
    return {
      store
    }
  },

  created() {
    this.getCharacters();
  },
  methods: {

    getCharacters() {
      this.store.loading = true;
      // axios.get("https://www.breakingbadapi.com/api/characters").then((resp) => {
      //   this.store.characters = resp.data;
      //   console.log(resp.data);



      //   this.store.loading = false;
      // })
      let apiUrl = "https://www.breakingbadapi.com/api/characters";

      const urlParams = {}

      if (this.store.searchCategory) {
        urlParams.category = this.store.searchCategory;
      }


      axios.get(apiUrl, { params: urlParams })
        .then((resp) => {
          // Qui gestiamo la risposta se tutto è andato bene
          this.store.characters = resp.data
          console.log(this.store.searchCategory);
        })
        .finally(() => {
          // Qui resetto loading a false perché i dati sono arrivati
          this.store.loading = false;
        })

    }



  }

}


</script>

<template>
  <AppHeader @performSearch="getCharacters" />
  <div class="container">
    <AppLoader v-if="store.loading" />
    <CharactersList v-else />
  </div>

</template>

<style lang="scss">
@use "./styles/general.scss" as *;
</style>
