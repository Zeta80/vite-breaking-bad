<script>
export default {
    name: "AppHeader"
}
</script>

<template>
    <header>
        <h1 class=" text-start header-title">BREAKING BAD</h1>
    </header>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

header {
    height: $header_height;
    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    background-image: linear-gradient(to bottom right, #16191b, #394551a1);
    border: 1px solid black;

    h1 {
        color: white;
        padding: 10px;
    }
}
</style>