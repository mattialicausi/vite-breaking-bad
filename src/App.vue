<template>

  <HeaderComponent title= "Breaking Bad Api"/>

  <MainComponent :characters ="characterList"/>
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
        loading : false
      }
    },

    methods: {
      getCharacters(){
        this.loading = true;
        axios.get(this.apiUrl).then(
          (res)=> {
            this.characterList = [...res.data];
            this.loading = false;
            
        }).catch((error)=> {
          this.loading = false;
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
