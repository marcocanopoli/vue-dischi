<template>
    <div>
        <select name="genres" id="genres">
            <option value="" @click="$emit('selectFilter', '')">Seleziona un {{ filterName }}</option>
            <option v-for="(filter, index) in filters" :key="index"
                    :value="filter"
                    @click="$emit('selectFilter', filter)">{{ filter }}</option>
        </select>
    </div>    
</template>

<script>
export default {
    name: 'Select',
    props: {
        filters: Array,
        filterName: String
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';
    
    select {          
        width: 200px;      
        padding: 5px;            
        font-size: 16px;
        margin-top: 10px;
        white-space: nowrap;
        text-overflow: ellipsis;
        color: $mainColor;
    }
</style>