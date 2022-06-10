<template>
    <main>
    <h3>Films</h3>
    <ul>
        <li class="" v-for="film in search.films" :key="film.id">{{film.title}} , {{film.original_title}} , {{film.original_language}} , {{film.vote_average}}</li>
    </ul>

    <h3>Tv Series</h3>
    <ul>
      <li class="" v-for="series in search.tvSeries" :key="series.id">{{series.name}} , {{series.original_name}} , {{series.original_language}} , {{series.vote_average}}</li>
    </ul>
    </main>
</template>

<script>

import search from "../Shared/shared";

export default {
    name: 'BaseMain',
    components: {
    },
    data(){
        return {
            search
        }
    },
}
</script>

<style lang="scss" scoped>

</style>