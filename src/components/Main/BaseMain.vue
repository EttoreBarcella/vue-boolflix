<template>
  <main>
    <h2>Films</h2>
    <ul class="film-list">
      <li v-for="film in search.films" :key="film.id">
        <BaseCard :info="film"/>
      </li>
    </ul>

    <h2>Tv Series</h2>
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
  background-color: var(--primary-color);
  h2{
    color: var(--tertiary-color);
  }
  .film-list, .tv-list{
    display: flex;
    flex-wrap: wrap;
    gap: 4rem;
      li{
        list-style: none;
        color: var(--tertiary-color);
        font-size: .75rem;
      }
  }
}
</style>