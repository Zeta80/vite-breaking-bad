<script>
import { store } from "../store";
export default {
    name: "AppHeader",
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <header>
        <div class="logo">
            <img src="../assets/logo.png" alt="">
        </div>
        <h1 class=" text-start header-title mb-4">Breaking Bad Api</h1>
        <div class="container ">
            <div class="select-bar">

                <select @change="$emit('performSearch')" v-model="store.searchCategory">
                    <option value="Breaking Bad">Breaking Bad</option>
                    <option value="Better Call Saul">Better call Saul</option>
                </select>
            </div>
        </div>
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
    border-bottom: 1px solid black;

    .logo {
        max-width: 200px;
        display: inline-block;
    }

    h1 {
        color: white;
        padding: 10px;
        display: inline-block;
    }

    .select-bar {
        margin-right: 100px;
    }
}
</style>