<template>
    <div id="app">
        <Header @search="performSearch" />
        <Main :Array1="movieList"
              :Array2="tvList"/>

    </div>
</template>

<script>
import axios from 'axios';
import Header from "@/components/Header.vue";
import Main from '@/components/Main.vue'

export default {
  name: 'App',
  components: {
      Header,
      Main,
  },

  data() {
      return {
        movieList: [],
        tvList: [],
      }
  },

  methods: {
    performSearch(searchText) {
      console.log(searchText);

      if (searchText !== '') {

          const apiParams = {
                api_key: '2115a7432b175478adeded346c457451',                          
                query: searchText,
                language: 'it-IT',
          }

          // MOVIES
          axios

            .get('https://api.themoviedb.org/3/search/movie', {

              params: apiParams,

            })

            .then(result => {
              this.movieList = result.data.results
            })

            .catch(err => console.log(err))


          // SERIE TV
          axios

            .get('https://api.themoviedb.org/3/search/tv', {

              params: apiParams,

            })

            .then(result => {
              this.tvList = result.data.results
            })

            .catch(err => console.log(err))

      }

    },

  },

};
</script>

<style lang="scss">
@import '@/styles/global.scss';
</style>
