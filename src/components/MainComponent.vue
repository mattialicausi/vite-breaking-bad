<template>
    <main class="container">

        <ShowCharacter/>


        <div class="row d-flex justify-content-center">

            <div class="loading-page mt-2 d-flex justify-content-center" v-if="store.loading">
                <div class="lds-circle p-2"><div></div></div>
            </div>

            <CardSection :character ="item" v-for="(item, index) in store.characterList" :key="item.char_id" v-if="!store.loading"/>

        </div>
        
    </main>
</template>

<script>
import CardSection from './main_section/CardSection.vue';
import ShowCharacter from './main_section/ShowCharacter.vue';
import {store} from '../store';

    export default {
    name: "MainComponent",
    components: { 
      ShowCharacter, 
        CardSection 
    },
    // props: [
    //     "characters",
    //     "loading"
    // ],

    data() {
      return {
        store,
      }
    }
   
}
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;

    main {
        margin: 0 auto;
        background-color: $white-text;
    }

    .loading-page{
        color: black;
    }

    //LOADER

    .lds-circle {
  display: inline-block;
  transform: translateZ(1px);
}
.lds-circle > div {
  display: inline-block;
  width: 64px;
  height: 64px;
  margin: 8px;
  border-radius: 50%;
  background: $description-card;
  animation: lds-circle 2.4s cubic-bezier(0, 0.2, 0.8, 1) infinite;
}
@keyframes lds-circle {
  0%, 100% {
    animation-timing-function: cubic-bezier(0.5, 0, 1, 0.5);
  }
  0% {
    transform: rotateY(0deg);
  }
  50% {
    transform: rotateY(1800deg);
    animation-timing-function: cubic-bezier(0, 0.5, 0.5, 1);
  }
  100% {
    transform: rotateY(3600deg);
  }
}




</style>