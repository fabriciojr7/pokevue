<script setup>
    const pokemon = defineProps(["name", "xp", "height", "img", "loading"])
</script>

<template>
    <div 
        class="card cardPokemonSelected"
        :class="loading ? '' : 'animate__animated animate__flipInY'"
    >        
        <img 
            :src="pokemon.img" 
            class="card-img-top pt-2"
            :alt="pokemon.name"
            height="250"
            v-if="pokemon.img"
        >
        <img 
            src="../assets/egg_pokemon.svg" 
            class="card-img-top pt-2"
            :alt="pokemon.name"
            height="250"
            v-else
        >

        <div class="card-body">
            <h5 class="card-title text-center">{{ pokemon.name || '???'}}</h5>
            <hr>
            <div class="row">
                <section class="col">
                    <strong>XP:</strong>
                    <span>{{pokemon.xp}}</span>
                </section>
                <section class="col">
                    <strong>Altura:</strong>
                    <span>{{ pokemon.height }}</span>
                </section>
            </div>            
        </div>
    </div>    
</template>

<style scoped>
    .cardPokemonSelected{
        height: 75vh;
        background: rgb(72,63,251);
        background: radial-gradient(circle, rgba(220,194,106,0.8) 0%, rgba(244,0,0,0.8) 100%);
    }

    .cardPokemonSelected img{
        height: 250px;
    }

    @media (max-width: 768px) {
        .cardPokemonSelected{
            height: 30vh;
            width: 50%;
            margin: 0 auto 10px auto;
        }
        .cardPokemonSelected img{
            height: 100px;
        }       
    }
</style>