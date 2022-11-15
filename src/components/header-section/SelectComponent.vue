<template>
    <div class="container rounded-2">
        <select class="p-1 rounded-2" name="" id="">
            <option selected value="">Choose...</option>
            <option value="" v-for="(category, index) in categoryOptions" :key="index">{{category}}</option>
        </select>
    </div>
</template>

<script>
import {store} from '../../store';

    export default {
        name: 'SelectComponent',

        data() {
            return {
                categoryOptions: [
                    'Breaking Bad',
                    'Better Call Saul'
                ],
            }
        }
    }
</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables' as *;


</style>