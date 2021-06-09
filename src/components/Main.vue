<template>
    <main>
        <Cards />
    </main>
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
    @import '../style/mixins.scss';

    main {
        @include flex-center('both');
        
        width: 100%;        
        min-height: calc(100% - #{$headerHeight});
        padding-top: 50px;
        background-color: $mainColor;
    }
</style>