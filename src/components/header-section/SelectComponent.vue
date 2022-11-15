<template>
    <div class="container rounded-2">
        <select class="p-1 rounded-2" name="search-category" id="search-category" v-model="store.search.category" @change="searchCharacters">
            <option selected value="">Choose...</option>
            <option :value="category" v-for="(category, index) in categoryOptions" :key="index">{{category}}</option>
        </select>
   
    </div>
</template>

<script>
import {store} from '../../store';

    export default {
        name: 'SelectComponent',

        data() {
            return {
                store,
                categoryOptions: [
                    'Breaking Bad',
                    'Better Call Saul'
                ],
            }
        },

        methods: {
            searchCharacters() {
                this.$emit('filterchar');
                console.log('click')
            },
        },





    }
</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables' as *;


</style>