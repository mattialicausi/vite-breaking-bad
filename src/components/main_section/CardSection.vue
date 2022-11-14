<template>
    <section>
        <div class="row mt-2">
            <div class="col-3 m-2 g-1 myCard text-center">
                <img src="#" alt="image">
                <h3>Nome</h3>
                <p>Description</p>
                
            </div>
          
         
        </div>
    </section>
</template>

<script>
    export default {
        name: 'CardSection',
    }
</script>

<style lang="scss">
@use '../../assets/styles/partials/variables' as *;

    .myCard {
        background-color: $bg-color;

        img {
            height: 200px;
            width: auto;
        }

        h3{
            color: $white-text;
        }

        p{
            color: $description-card;
        }
    }

  


</style>