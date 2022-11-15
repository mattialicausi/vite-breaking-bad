<template>

  <HeaderComponent title= "Breaking Bad Api"/>

     <section>
            <SelectComponent @filterchar="getCharacters"/>
      </section>

      <div v-if="store.errormessage">
        <h1>Qualcosa è andato storto</h1>
        <p>{{store.errormessage}}</p>
      </div>

  <MainComponent :characters ="store.characterList"/>
</template>

<script>

import axios from 'axios';
import HeaderComponent from './components/HeaderComponent.vue';
import SelectComponent from './components/header-section/SelectComponent.vue'
import MainComponent from './components/MainComponent.vue';
import {store} from './store';

  export default {
    components: { 
      HeaderComponent,
      SelectComponent,
      MainComponent
    },

    data (){
      return {
        store,
        endPoint : ''

      }
    },

    methods: {
      getCharacters(){
        store.errormessage = '';

        let options = null;

        if(store.search.category){
          options = {
            params: {
              ...store.search
            }
          }
        }

      this.store.loading = true;
      const apiurl = store.apiUrl + this.endPoint;

        axios.get(apiurl, options).then(
          (res)=> {
            store.characterList = res.data;
            store.loading = false;        
          
            
        }).catch((error)=> {
         store.characterList.length = 0;

          store.loading = false;
          store.errormessage = error.message

        })
        
      },
    
    },

    created() {
      this.getCharacters();
    }

}
</script>

<style lang="scss" scoped>

</style>
