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

    <div class="container">
        <div class="wrapper">
            <div class="found-characters">
                <h3>Found {{ store.characters.length }} characters</h3>
            </div>
            <div class="row row-cols-2 row-cols-md-4 row-cols-ld-5 g-3">
                <div class="col" v-for="character in store.characters" :key="character.id">
                    <CharacterCard :character="character" />
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

.container {
    background-color: white;

    .wrapper {
        width: 90%;
        margin: $header_height auto 50px;
        padding: 40px 0;

        .found-characters {
            width: 100%;
            background-color: #212529;
            color: white;
            margin-bottom: 1em;
            padding: 0.5rem;
        }
    }
}
</style>