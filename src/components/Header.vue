<template>
    <header class="header">

        <div class="top">

            <div class="sec left">
                <img src="https://fontmeme.com/permalink/211208/6bcb0c41d7009b6fd82ae769632e5a03.png" alt="netflix-font" border="0">
                <!-- <div class="link">
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
                </div> -->
                
            </div>


            <div class="sec right">

                <div class="search-container">

                    <input 
                    type="text" 
                    placeholder="Search a movie" 
                    v-model.trim="searchText"
                    @keyup.enter="$emit('search', searchText)"
                    />

                    <button class="button" @click="$emit('search', searchText)"><i class="fas fa-search"></i></button>

                </div>
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
        display: flex;
        justify-content: space-between;
        width: 100%;
        position: fixed;
        z-index: 3;


        .top {
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: space-between;

            // a {
            //     text-decoration: none;
            //     color: lightgrey;
            //     font-weight: 700;
            //     font-size: 0.8rem;
            // }

            .sec {
                display: flex;
                color: lightgrey;
            }

            .left {
                display: flex;
                background-color: #1e262d;

                img {
                    width: 20%;

                    margin: 20px;
                }

            }

            .right {
                display: flex;
                justify-content: flex-end;
            }

            input {
                background: transparent;
                border: none;
                border-bottom-color: currentcolor;
                border-bottom-style: none;
                border-bottom-width: medium;
                border-bottom: 1px solid;
                color: lightgrey;
                font-size: 0.8rem;
            }

            .button {
                font-size: 0.8rem;
            }
 
        }
    }

</style>