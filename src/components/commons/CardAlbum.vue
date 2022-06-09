<template>
    <div class="singleCard">
        <img :src="card.poster" :alt="card.title">
        <h5>{{card.title}}</h5>
        <small>{{card.author}}</small>
        <div>{{card.year}}</div>
    </div>
</template>

<script>
export default {
    name: 'CardAlbum',
    props: {
        card: Object,
    }
}
</script>

<style lang="scss" scoped>
    .singleCard {
        background-color: var(--primary-color);
        text-align: center;
        
        img {
           width: 90%;
           padding: 20px;
        }

        h5 {
           color: white;
        }

        small, div {
            color: lightgrey;
        }
    }
</style>