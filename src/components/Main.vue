<template>

    <section class="section">    
        <aside class="aside">

            <span class="naviga">NAVIGA</span>
            
            <ul class="filter-list">
                <li class="filter-container">
                    <a class="filter" href="#"><i class="fas fa-home"></i> Home</a>
                </li>

                <li class="filter-container">
                    <a class="filter" href="#"><i class="fas fa-video"></i> Film</a>
                </li>
                
                <li class="filter-container">
                    <a class="filter" href="#"><i class="fas fa-tv"></i> Serie TV</a>
                </li>
                                
                <li class="filter-container">
                    <a class="filter" href="#"><i class="fas fa-dragon"></i> Anime</a>
                </li>
                
                <li class="filter-container">
                    <a class="filter" href="#"><i class="fab fa-hotjar"></i> Popolari</a>
                </li>
                
                <li class="filter-container">
                    <a class="filter" href="#"><i class="fas fa-star"></i> I più Votati</a>
                </li>
                
                <li class="filter-container">
                    <a class="filter" href="#"><i class="fas fa-list"></i> Film A-Z</a>
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
        padding-top: 60px;
        display: flex;
        justify-content: center;
        height: 100vh;
        margin: 0 auto;
        color: grey;
        font-weight: 700;
        font-size: 0.8rem;

        main {
            padding: 40px;
            display: flex;
        }

        .aside {
            width: 20%;
            padding: 20px;
            margin: 90px 0 0 5%;
        }

            .filter-list {
                margin: 20px 0 50px -25px;
                list-style: none;
                height: max-content;
                overflow: hidden;
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

                        a {
                            font-size: 0.8rem;
                        }

                        i {
                            margin-right: 10px;
                        }
                    }

                }

        .main {
            display: flex;
            overflow: auto;
        }

        .years {
            width: 100%;
        }

        .years ul {
            width: 100%;
            list-style: none;
            display: flex;
            flex-wrap: wrap;
            padding: 1rem;
            margin-top: 15px;

            li {
                background-color: lightgrey;
                width: 31%;
                margin: 2px auto;
                text-align: center;
                padding: 2px 0 1px 0;

                &:hover {
                    background-color :transparent;
                    color: lightgray
                }

            }
        }
    }

</style>