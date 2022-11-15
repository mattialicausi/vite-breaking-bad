<template>
            <div class="col-12 col-md-3 col-lg-2 m-1 g-1 rounded-2 myCard text-center">
                <div class="container-img d-flex justify-content-center">
                    <img class="img-fluid" :src="character.img" :alt="character.name">
                </div>
                <h3>{{character.name}}</h3>
                <p>{{character.category}}</p>
                <p>{{character.status}}</p>
            </div>
</template>

<script>
import {store} from '../../store';

    export default {
        name: 'CardSection',
        props: {
            character : Object
        },

        data() {
            return {
                store,
            }
        }
    }
</script>

<style lang="scss">
@use '../../assets/styles/partials/variables' as *;

    .myCard {
        background-color: $bg-color;
        margin: 0 auto;

        .container-img{
            width: auto;
            height: 65%;
            margin: 10px;
        }

        h3{
            color: $white-text;
        }

        p{
            color: $description-card;
        }
    }

</style>