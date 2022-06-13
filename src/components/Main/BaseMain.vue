<template>
  <main>
    <h4>Films</h4>
    <ul class="film-list">
      <li v-for="film in search.films" :key="film.id">
        <BaseCard :info="film"/>
      </li>
    </ul>

    <h4>Tv Series</h4>
    <ul class="tv-list">
      <li v-for="serie in search.tvSeries" :key="serie.id">
        <BaseCard :info="serie"/>
      </li>
    </ul>
  </main>
</template>

<script>

import search from "../Shared/shared";
import BaseCard from '../Common/BaseCard.vue';

export default {
    name: 'BaseMain',
    components: {
        BaseCard
    },
    data(){
        return {
            search
        }
    },
}
</script>

<style lang="scss" scoped>
main{
    .film-list, .tv-list{
        list-style: none;
    }
}
</style>