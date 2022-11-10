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
            <div class="row row-cols-2 row-cols-md-4 row-cols-ld-5 g-3">
                <div class="col" v-for="character in store.characters" :key="character.id">
                    <CharacterCard :character="character" />
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.container {
    background-color: white;

    .wrapper {
        width: 90%;
        margin: 0 auto;
        padding-top: 80px;
    }
}
</style>