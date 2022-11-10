<script>
export default {
    name: "CharacterCard",
    props: {
        character: String
    }
}
</script>

<template>
    <div class="character-item text-center">
        <!-- <img :src="character.img" alt=""> -->
        <h4>{{ character }}</h4>
        <h4>ciao</h4>
    </div>
</template>

<style lang="scss" scoped>

</style>