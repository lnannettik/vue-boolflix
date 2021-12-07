<template>

    <section class="section">    
        <aside class="aside">NAVIGA
            <ul class="filter-list">
                <li class="filter-container">
                    <a class="filter" href="#">Home</a>
                </li>

                <li class="filter-container">
                    <a class="filter" href="#">Film</a>
                </li>
                
                <li class="filter-container">
                    <a class="filter" href="#">Serie TV</a>
                </li>
                
                <li class="filter-container">
                    <a class="filter" href="#">TV Show</a>
                </li>
                
                <li class="filter-container">
                    <a class="filter" href="#">Anime</a>
                </li>
                
                <li class="filter-container">
                    <a class="filter" href="#">Popolari</a>
                </li>
                
                <li class="filter-container">
                    <a class="filter" href="#">I più Votati</a>
                </li>
                
                <li class="filter-container">
                    <a class="filter" href="#">Film A-Z</a>
                </li>
                                
            </ul>

            <div class="years"> FILTER by YEAR
                <ul>
                    <li>2021</li>
                    <li>2020</li>
                    <li>2019</li>

                    <li>2018</li>
                    <li>2017</li>
                    <li>2016</li>

                    <li>2015</li>
                    <li>2014</li>
                    <li>2013</li>

                    <li>2012</li>
                    <li>2011</li>
                    <li @click="$emit('search', searchText)">2010</li>
                </ul>
            </div>

        </aside>

        <main class="main">
          <CardList :list="Array1" />

          <CardList :list="Array2" />            
        </main>

    </section>

</template>

<script>
import CardList from "@/components/CardList.vue";


export default {
    name: 'Main',

    components: {
        CardList,
    },

    props: {
        Array1: Array,
        Array2: Array,
    },

}
</script>

<style scoped lang="scss">
    .section {
        padding-top: 90px;
        display: flex;
        height: 100vh;
        width: 70%;
        margin: 0 auto;
        color: grey;
        font-weight: 700;

        main {
            padding: 40px;
        }

        .aside {
            background-color: #1e262d;
            width: 20%;
            padding: 20px;
        }

            .filter-list {
                margin: 20px 0 50px -25px;
                list-style: none;
            }

                .filter-container {
                    padding: 8px;

                    &:hover .filter {
                        color: white;
                    }

                    &:hover {
                        background-color: #171d22;
                    }

                    .filter {
                        text-decoration: none;
                        color: lightgrey;
                    }

                }

        .main {
            background-color: #171d22;
            display: flex;
            overflow: auto;
        }

        .years {
            width: 100%;
            // border: 1px solid black;

        }

        .years ul {
            width: 100%;
            list-style: none;
            display: flex;
            flex-wrap: wrap;
            padding: 1rem;
            margin: 20px 0;

            li {
                background-color: lightgrey;
                width: 31%;
                margin: 2px auto;
                text-align: center;

                &:hover {
                    background-color :transparent;
                }

            }
        }
    }

</style>