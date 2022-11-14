<template>

  <HeaderComponent title= "Breaking Bad Api"/>

  <MainComponent />
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';

  export default {
    components: { 
      HeaderComponent,
      MainComponent
    }
}
</script>

<style lang="scss" scoped>

</style>
