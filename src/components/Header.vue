<template>
    <header>
        <input type="text" placeholder="Search a movie" v-model="searchText" />

        <button>Search</button>
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

<style>

</style>