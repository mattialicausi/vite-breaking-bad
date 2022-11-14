<template>

  <HeaderComponent title= "Breaking Bad Api"/>

  <MainComponent />
</template>

<script>
import axios from 'axios';
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';

  export default {
    components: { 
      HeaderComponent,
      MainComponent
    },

    data (){
      return {
        apiUrl : 'https://www.breakingbadapi.com/api/characters',
        characterList: [],

      }
    },

    methods: {
      getCharacters(){
        axios.get(this.apiUrl).then(
          (res)=> {
            this.characterList = [...res.data];
            console.log(this.characterList);

        })
      }
    },

    created() {
      this.getCharacters();
    }

}
</script>

<style lang="scss" scoped>

</style>
