<script>
import { store } from "../store";
import CharacterCard from "../components/CharacterCard.vue";
export default {
    name: "CharactersList",
    components: {
        CharacterCard
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <h2 class="text-center">Lista personaggi breaking bad</h2>

    <div class="row row-cols-2 row-cols-md-4 g-3">
        <div class="col" v-for="character in store.characters" :key="character.id">
            <CharacterCard :character="character.name" />
        </div>
    </div>
</template>

<style lang="scss" scoped>

</style>