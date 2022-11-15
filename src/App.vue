<template>

  <HeaderComponent title= "Breaking Bad Api"/>

  <MainComponent :characters ="store.characterList"/>
</template>

<script>
import axios from 'axios';
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import {store} from './store';

  export default {
    components: { 
      HeaderComponent,
      MainComponent
    },

    data (){
      return {
        store,
      }
    },

    methods: {
      getCharacters(){
        this.store.loading = true;
        console.log(this.store.loading)

        axios.get(this.store.apiUrl).then(
          (res)=> {
            this.store.characterList = [...res.data];
            this.store.loading = false;        
            console.log(this.store.loading)
            
        }).catch((error)=> {
          this.store.loading = false;
          console.log(error);

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
