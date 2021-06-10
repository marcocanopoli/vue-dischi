<template>
    <div class="main-wrapper">
        <div class="container">            
            <div class="cards" v-if="loaded">
                <div class="filters">
                    <Select @selectFilter="getSelected"
                        :filters="getArtists"
                        :filter-name="'artista'"/>
                    <Select @selectFilter="getSelected"
                        :filters="getGenres"
                        :filter-name="'genere'"/>
                </div>
                <Card   v-for="(album, index) in filteredAlbums" :key="index"
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
import Select from './Select.vue';
import axios from 'axios' ;

export default {
    name: 'Cards',
    components: {
        Card,
        Loader,
        Select
    },
    data() {
        return {
            albums: [],
            loaded: false,
            filter: '',
            artists: [],
            genres: []
        }
    },
    methods: {        
        getSelected (select) {
            this.filter = select;
        }
    },
    computed: {
        getGenres() {
            const genres = [];
            this.albums.forEach ((album) => {
                if (!genres.includes(album.genre)) {
                    genres.push(album.genre);
                    this.genres.push(album.genre);
                }
            });            
            return genres;
        },
        getArtists() {
            const artists = [];
            this.albums.forEach ((album) => {
                if (!artists.includes(album.author)) {
                    artists.push(album.author);
                    this.artists.push(album.author);
                }
            });
            return artists;
        },
        filteredAlbums() {
            let filtered = [];
            if (this.filter == '') {
                filtered = this.albums;
            } else if (this.genres.includes(this.filter) ){
                filtered = this.albums.filter((album) => album.genre == this.filter);
            } else if (this.artists.includes(this.filter)){
                filtered = this.albums.filter((album) => album.author == this.filter);
            }
            return filtered;
        }
    },
    created() {
        axios
            .get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((res) => {
                this.albums = res.data.response;
                this.loaded = true;
            });
    }
}
</script>

<style lang="scss">
    @import '../style/mixins.scss';

    .filters {
        display: flex;
        flex-direction: column;
        align-items: flex-end;
        width: 100%;
        margin-bottom: 25px;
    }
    .cards {
        @include flex-center ('horizontal');
        flex-wrap: wrap;
        width: 100%; 
    }
</style>