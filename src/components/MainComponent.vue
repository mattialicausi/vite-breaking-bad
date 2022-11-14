<template>
    <main class="container">

        <SearchApp/>

        <div class="loading-page" v-if="loading">
            carica
        </div>

        <div class="row d-flex justify-content-center" v-if="!loading">

            <CardSection :character ="item" v-for="(item, index) in characters" :key="item.char_id"/>

        </div>
        
    </main>
</template>

<script>
import CardSection from './main_section/CardSection.vue';
import SearchApp from './main_section/SearchApp.vue';

    export default {
    name: "MainComponent",
    components: { 
        SearchApp, 
        CardSection 
    },
    props: [
        "characters"
    ]
}
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;

    main {
        margin: 0 auto;
        background-color: $white-text;
    }



</style>