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
import {store} from './store';
import axios from 'axios';
import HeaderComponent from './components/HeaderComponent.vue';
import SelectComponent from './components/header-section/SelectComponent.vue'
import MainComponent from './components/MainComponent.vue';


  export default {
    components: { 
      HeaderComponent,
      SelectComponent,
      MainComponent
    },

    data (){
      return {
        store,
        endPoint : 'category'

      }
    },

    methods: {
      getCharacters(){
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

        axios.get(this.store.apiUrl).then(
          (res)=> {
            this.store.characterList = [...res.data];
            this.store.loading = false;        
          
            
        }).catch((error)=> {
          this.store.loading = false;
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
