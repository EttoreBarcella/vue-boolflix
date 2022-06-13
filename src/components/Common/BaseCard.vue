<template>
    <div class="card">
        <img class="card__img" :src="img(info.poster_path)" :alt="info.title || info.name">
        <h3 v-if="info.title">{{info.title}}</h3>
        <h3 v-else>{{info.name}}</h3>
        <h4 class="card__title">{{info.original_title ? info.original_title : info.original_name}}</h4>
        <div class="card__vote" v-html="vote(info.vote_average)"></div>
        <p>
            <img width="30" v-if="flag(info.original_language)" :src="require(`../../assets/Img/${info.original_language}.png`)" :alt="info.original_language">
            <img width="30" v-else src="../../assets/Img/pace.png" alt="placeholder">
        </p>
    </div>
</template>

<script>
export default {
    name: 'BaseCard',
    props: {
        info: Object,
    },
    data() {
        return {
            flagsAvailable: [
                'en'
            ]
        }
    },
    methods: {
        flag(lang) {
            return this.flagsAvailable.includes(lang);
        },
        img(url){
            if (url == null){
                return `https://via.placeholder.com/185x260?text=No image`;
            }
            return `https://image.tmdb.org/t/p/w185/${url}`;
        },
        vote(voto) {
            let fullStars = '';
            let emptyStars = '';
            for (let i = 0; i < Math.ceil(voto / 2); i++) {
                fullStars += '<i style="color:gold" class="icon-color fas fa-star"></i>';
            }
            for (let i = 0; i < (5 - Math.ceil(voto / 2)); i++) {
                emptyStars += '<i class="fas fa-star vuoto"></i>';
            }   
            return `${fullStars}${emptyStars}`;
        }
    }
}
</script>

<style lang="scss" scoped>

</style>