<template>
    <section class="mt-3 p-3 text-center" v-if="!store.loading">
      <h4>Founded {{store.characterList.length}} characters</h4>
    </section>
</template>

<script>
import {store} from '../../store';
    export default {
        name: 'ShowCharacter',

        data(){
            return {
                store
            }
        }
        
    }
</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables' as *;


</style>