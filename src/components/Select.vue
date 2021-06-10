<template>
    <div>
        <select name="genres" id="genres">
            <option value="" @click="$emit('selectFilter', '')">Seleziona un genere</option>
            <option v-for="(genre, index) in genres" :key="index"
                    :value="genre"
                    @click="$emit('selectFilter', genre)">{{ genre }}</option>
        </select>
        <select name="artists" id="artists">
            <option value="" @click="$emit('selectFilter', '')">Seleziona un artista</option>
            <option v-for="(artist, index) in artists" :key="index"
                    :value="artist"
                    @click="$emit('selectFilter', artist)">{{ artist }}</option>
        </select>
    </div>    
</template>

<script>
export default {
    name: 'Select',
    props: {
        genres: Array,
        artists: Array
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';

    select{          
        width: 200px;      
        padding: 5px;
        margin-bottom: 25px;
        font-size: 16px;
        white-space: nowrap;
        text-overflow: ellipsis;
        color: $mainColor;
    }
</style>