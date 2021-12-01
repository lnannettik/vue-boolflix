<template>

    <div class="card">
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
        }
    }

}
</script>

<style scoped lang="scss">
    .card {
        .flag img {
            width: 30px;
        }
    }
    

</style>