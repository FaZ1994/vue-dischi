<template>
    <header>
        <img src="../assets/img/logo.png" alt="Spotify's Logo">
    </header>
</template>

<script>
export default {
    nome: "AppHeader",
    props:{
        msg: String
    }
}
</script>

<style lang="scss" scoped>
@import "../style/general";

header {
    background-color: $mainColor;
    height: 70px;
    width: 100%;
    display: flex;
    align-items: center;
    position: sticky;
    top: 0;
    img {
        height: 50px;
        margin-left: 20px;
    }

}
</style>