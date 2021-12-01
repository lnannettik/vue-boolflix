<template>

    <div class="crd">
        <img 
            :src="`https://image.tmdb.org/t/p/w342${poster}`" 
            :alt="title"
        />
        <ul>
            <li>Titolo: {{ title }}</li>
            <li>Titolo Originale: {{ originalTitle }}</li>
            <li>
                Lingua: 
                <img class="flag"
                v-if="isFlag" 
                :src="require(`../assets/${language}.png`)" 
                :alt="language"
                >
                <span v-else>{{ language }}</span>
            </li>
            <li>voto: {{ vote }}</li>
            <li>
                <i :key="index" v-for="index in (Math.round(vote / 2))" class="fas fa-star"></i>
                <i :key="index" v-for="index in 5 - (Math.round(vote / 2))" class="far fa-star"></i>
            </li>
            
            
        </ul>
    </div>

</template>

<script>
export default {
    name: 'Card',
    props: {
        poster: String,
        title: String,
        originalTitle: String,
        language: String,
        vote: Number,
    },
    data() {
        return {
            availableFlags: ['it', 'en']
        }
    },
    computed: {
        isFlag() {
            return this.availableFlags.includes(this.language);
        },
    }

}
</script>

<style scoped lang="scss">
    .crd {
        .flag {
            width: 30px;
        }
    }

    li i {
        color: black;
    }
    

</style>