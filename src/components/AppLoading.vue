
<script>
export default {
    name: "AppLoader"
}
</script>



<template>
    <div class="container">
        <div class="wrapper">
            <div class="lds-ripple">
                <div></div>
                <div></div>
            </div>

        </div>
    </div>
</template>


<style lang="scss" scoped>
.wrapper {
    margin-top: 200px;
    display: flex;
    justify-content: start;
    align-items: center;
}

.lds-ripple {
    display: inline-block;
    position: relative;
    width: 280px;
    height: 280px;
}

.lds-ripple div {
    position: absolute;
    border: 4px solid #fff;
    opacity: 1;
    border-radius: 50%;
    animation: lds-ripple 1s cubic-bezier(0, 0.2, 0.8, 1) infinite;
}

.lds-ripple div:nth-child(2) {
    animation-delay: -0.6s;
}

@keyframes lds-ripple {
    0% {
        top: 136px;
        left: 136px;
        width: 0;
        height: 0;
        opacity: 0;
    }

    4.9% {
        top: 136px;
        left: 136px;
        width: 0;
        height: 0;
        opacity: 0;
    }

    5% {
        top: 136px;
        left: 136px;
        width: 0;
        height: 0;
        opacity: 1;
    }

    100% {
        top: 0px;
        left: 0px;
        width: 282px;
        height: 282px;
        opacity: 0;
    }
}
</style>