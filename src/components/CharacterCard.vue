<script>
export default {
    name: "CharacterCard",
    props: {
        character: Object
    }
}
</script>

<template>
    <div class="character-item text-center">
        <img :src="character.img" alt="">
        <h4>{{ character.name }}</h4>
        <h4>ciao</h4>
    </div>
</template>

<style lang="scss" scoped>

</style>