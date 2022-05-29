<template>
    <section>

        <div id="popup-container"></div>

    </section>
</template>

<script>
export default {
    name: 'AquelarrePopUp'
}
</script>

<style scoped>
section{
    width: 100%;
    height: 100vh;
    z-index: 1;
    position: fixed;
    display: flex;
    align-items: center;
    justify-content: center;
}

#popup-container{
    width: 80vw;
    height: 80vh;
    border-radius: 2vw;
    background-color: rgba(0,0,0, 30%);
    -webkit-backdrop-filter: blur(10px);
    backdrop-filter: blur(10px);
    -moz-backdrop-filter: blur(10px);
}

.popup-appear{
    animation-name: popup-appear_ !important;
    animation-duration: 1s;
    animation-fill-mode: forwards;
}

.popup-dissapear{
    animation-name: popup-disappear_;
    animation-duration: 1s;
}

@keyframes popup-appear_{
    0%{
        transform: scaleX(0) scaleY(0);
    }
    30%{
        transform: scaleX(1) scaleY(0.1);
    }
    100%{
        transform: scaleX(1) scaleY(1);
    }
}
</style>