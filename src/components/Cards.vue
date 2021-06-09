<template>
    <div class="main-wrapper">
        <div class="container">
            <div class="cards" v-if="loaded">
                <Card   v-for="(album, index) in albums" :key="index"
                    :title="album.title"
                    :author="album.author"
                    :year="album.year"
                    :img-url="album.poster"/>  
            </div>
            <Loader v-else />
        </div>
    </div>
</template>

<script>
import Card from './Card.vue';
import Loader from './Loader.vue';
import axios from 'axios' ;

export default {
    name: 'Cards',
    components: {
        Card,
        Loader
    },
    data() {
        return {
            albums: [],
            loaded: false
        }
    },
    created() {
        axios
            .get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((res) => {
                this.albums = res.data.response;
                setTimeout(() => {
                    this.loaded = true;
                }, 3000)
            });
    }
}
</script>

<style lang="scss" scoped>
    .cards {
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        width: 100%; 
    }
</style>