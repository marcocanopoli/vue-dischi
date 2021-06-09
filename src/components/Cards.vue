<template>
    <div>
        <Card />
    </div>
</template>

<script>
import Card from './Card.vue';
import axios from 'axios' ;

export default {
    name: 'Cards',
    components: {
        Card
    },
    created() {
        axios
            .get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((res) => {
                console.log(res);
            });
    }
}
</script>

<style>

</style>