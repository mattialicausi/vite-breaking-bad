<template>
    <main class="container">
        <SearchApp/>

        <CardSection/>
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
    }
}
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;

    main {
        margin: 0 auto;
        background-color: $white-text;
    }


</style>