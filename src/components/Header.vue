<template>
    <header class="header">

        <div class="top">

            <div class="sec left">
                <img src="https://fontmeme.com/permalink/211208/6bcb0c41d7009b6fd82ae769632e5a03.png" alt="netflix-font" border="0">
            </div>


            <div class="sec right col-3 col-mg-6 col-lg-6">

                <div class="search-container">

                    <input 
                    class="input"
                    type="text" 
                    placeholder="Search a movie or series..." 
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
        margin-top: 2rem;


        .top {
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: space-between;

            .sec {
                display: flex;
                color: lightgrey;
            }

            .left {
                display: flex;
                margin-left: 5%;

                img {
                    width: 80%; 
                    margin: 20px;
                }

            }

            .right {
                display: flex;
                justify-content: flex-end;
                margin-right: 10%;

                .search-container {
                    display: flex;
                    width: 0;
                    justify-content: end;
                    transition: width 500ms ease;
                    border-radius: 40px;
                    padding: 10px 30px;                    

                    &:hover,
                    &:focus {
                        background: #171d22;
                        width: 100%;

                    }

                    .input {
                        width: 100%;
                        border: none;
                        color: lightgrey;
                        font-size: 0.7rem;
                        font-weight: 700;
                        background: #171d22;
                        border-radius: 20px;
                        
                    }

                    .button {
                        font-size: 0.8rem;
                        font-size: xx-large;
                        background: transparent;
                        border: none;
                        color: lightgray;
                        margin-left: 20px;
                        z-index: 4;

                    
                    }

                }
            }
 
        }
    }

</style>