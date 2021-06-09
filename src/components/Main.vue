<template>
    <div>
        <div class="container">
            <Cards />
        </div>
    </div>
</template>

<script>
import Cards from './Cards.vue';

export default {
    name: 'Main',
    components: {
        Cards
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';

    div {
        height: calc(100% - #{$headerHeight});
        width: 100%;
        background-color: $mainColor;

        div {
            padding: 50px 0;
        }
    }
</style>