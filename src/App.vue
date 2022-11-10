<script >
import axios from "axios";
import { store } from "./store";
import AppHeader from './components/AppHeader.vue';
import CharactersList from './components/CharacterList.vue';


export default {
  components: {
    AppHeader,
    CharactersList
  },

  data() {
    return {
      store
    }
  },

  created() {

    axios.get("https://www.breakingbadapi.com/api/characters").then((resp) => {
      this.store.characters = resp.data;
      console.log(resp.data);

    });
  }
}

</script>

<template>
  <AppHeader />
  <div class="container">
    <CharactersList />
  </div>

</template>

<style lang="scss">
@use "./styles/general.scss" as *;
</style>
