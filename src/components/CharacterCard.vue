<script>
export default {
    name: "CharacterCard",
    props: {
        character: Object
    }
}
</script>

<template>
    <div class="character-item">
        <img :src="character.img" alt="">
        <div class="text d-flex flex-column align-items-center">
            <h4>{{ character.name }}</h4>
            <h4>{{ character.status }}</h4>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.character-item {
    background-color: #2e3a46;
    padding: 15px;
    height: 100%;

    .text {
        margin-top: 20px;

        h4 {
            color: white;
            margin-top: 0.6rem;


            &:last-child {
                color: #716b67;
            }
        }
    }


}
</style>