<template>
    <div>
        <img src="../assets/img/spotify.png" alt="Spotify Logo">
    </div>
</template>

<script>

export default {
    name: 'Header'    
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';
    @import '../style/mixins.scss';

    div {
        @include flex-center ('vertical');
        
        height: 65px;
        width: 100%;
        background-color: $secondColor;

        img {
            height: 70%;
            margin-left: 20px;
        }
    }
</style>