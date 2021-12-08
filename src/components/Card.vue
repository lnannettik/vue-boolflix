<template>

    <div class="crd" >
        <img 
            v-if="poster !== null"
            :src="`https://image.tmdb.org/t/p/w185${poster}`" 
            :alt="title"
        />

        <span v-else>immagine non disponibile</span>
       
        <div class="crd-contenuto">
            <ul>
                <li class="title">{{ title }}</li>
                <li>Titolo Originale: {{ originalTitle }}</li>
                <li v-if="poster !== null">{{ overview }}</li>

                <!-- <li>
                    Lingua: 
                    <img class="flag"
                    v-if="isFlag" 
                    :src="require(`../assets/${language}.png`)" 
                    :alt="language"
                    >
                    <span v-else>{{ language }}</span>
                </li> -->
                <li>voto: {{ vote }}</li>
                <li>
                    <i :key="`star-${index}`" v-for="(el, index) in (Math.round(vote / 2))" class="fas fa-star"></i>
                    <i :key="`empty-star-${index}`" v-for="(el, index) in 5 - (Math.round(vote / 2))" class="far fa-star"></i>
                </li>
                                
            </ul>
        </div>


    </div>

</template>

<script>
export default {
    name: 'Card',
    props: {
        poster: String,
        title: String,
        originalTitle: String,
        overview: String,
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
        // width: 185px;
        border-radius: 10px;
        font-size: 10px;
        margin: 40px;
        position: relative;
        overflow: hidden;
        transition: transform 500ms ease;
        background-color: black;

        &:hover {
            transform: scale(1.05);
        }

        &:hover .crd-contenuto {
            padding-top: 10px;
            height: 100%;
            top: 0;
        }
        
        img {
            border-radius: 10px;
            z-index: 1;
        }

        .crd-contenuto {
            // height: 60%;
            width: 100%;
            background: linear-gradient(
                        hsl(0 0% 0% / 1),
                        hsl(20 0% 0% / 0.3) 90%,
                        hsl(0 0% 0% / 0)
                        );
            position: absolute;
            padding-right: 5%;
            padding-top: 10px;
            z-index: 2;
            left: 0;
            top: 100%;
            transition: top 500ms ease;

        }

        .flag {
            width: 8px;
        }

        ul {
            list-style: none;
            margin-left: -20px;

            .title {
                margin-bottom: 10px;
                font-size: 1.5em;
                color: white;

            }
        }
    }

    

    li {
        color:white;
        margin-bottom: 10px;
    }


</style>