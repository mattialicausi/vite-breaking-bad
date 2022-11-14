<template>
    <header>
        <h1>{{title}}</h1>

        <section>
            <SelectComponent/>
        </section>
    </header>
</template>

<script>
import SelectComponent from './header-section/SelectComponent.vue';


    export default {
    name: "HeaderComponent",
    props: {
        title: String
    },
    components: { SelectComponent }
}
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;

    h1{
        font-weight: 700;
        color: $white-text;
        margin-left: 20px;
    }
</style>