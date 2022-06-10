<template>
  <header>
    <form @submit.prevent="submit()">                     
        <input class="" type="text" placeholder="Inserisci il nome del film" v-model="searchBar">
        <button type="submit">Cerca</button>                 
    </form>
  </header>
</template>

<script>

import axios from 'axios';
import search from "../Shared/shared";

export default {
    name: 'BaseHeader',
    data(){
        return {
            searchBar: '',
            search
        }
    },
     methods: {
        submit() {
            axios.get('https://api.themoviedb.org/3/search/movie',
                {
                    params: {
                        api_key: '112b28775dc802b91f74915e05422005',
                        query: this.searchBar,
                        language: 'it-IT'
                    }
                }
            ).then((response) => {
                search.films = response.data.results;
            }).catch((error) => {
                console.log(error);
            }),
            axios.get('https://api.themoviedb.org/3/search/tv',
                {
                    params: {
                        api_key: '112b28775dc802b91f74915e05422005',
                        query: this.searchBar,
                        language: 'it-IT'
                    }
                }
                ).then((response) => {
                    search.tvSeries = response.data.results;
                }).catch((error) => {
                    console.log(error);
            })
        }
    }
}
</script>

<style lang="scss" scoped>

</style>