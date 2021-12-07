<template>
    <header class="header">

        <div class="top">

            <div class="sec left">
                <div class="link">
                    <a href="">Home</a>
                </div>
                
                <div class="link">
                    <a href="">Film A - Z</a>
                </div>
                
                <div class="link">
                    <a href="">Serie TV</a>
                </div>
                
                <div class="link">
                    <a href="">Coming Soon</a>
                </div>
                
            </div>

            <div class="sec center">BOOLFLIX</div>

            <div class="sec right">

                <input 
                type="text" 
                placeholder="Search a movie" 
                v-model.trim="searchText"
                @keyup.enter="$emit('search', searchText)"
                />

                <button class="button" @click="$emit('search', searchText)">Search</button>

            </div>

        </div>

    </header>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            searchText: '',
        };
    },
};

</script>

<style scoped lang="scss">

    header {
        background-color: #262f37;
        display: flex;
        justify-content: space-evenly;
        width: 100%;
        position: fixed;

        .top {
            width: 70%;
            height: 90px;
            display: flex;
            background-color: #262f37;
            align-items: center;

            a {
                text-decoration: none;
                color: lightgrey;
                font-weight: 700;
                

            }

            .sec {
                display: flex;
                justify-content: center;
                color: lightgrey;
                width: 33%;
            }

            .left {
                display: flex;

                .link {
                    margin-right: 2vw;
                }
            }

            input {
                background: transparent;
                border: none;
                border-bottom-color: currentcolor;
                border-bottom-style: none;
                border-bottom-width: medium;
                border-bottom: 1px solid;
                color: lightgrey;
            }


            
        }
    }

</style>