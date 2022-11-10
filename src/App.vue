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
    this.store.loading = true;
    axios.get("https://www.breakingbadapi.com/api/characters").then((resp) => {
      this.store.characters = resp.data;
      console.log(resp.data);
      this.store.loading = false;
    });
  }
}

</script>

<template>
  <AppHeader />
  <div class="container">
    <AppLoader v-if="store.loading" />
    <CharactersList v-else />
  </div>

</template>

<style lang="scss">
@use "./styles/general.scss" as *;
</style>
