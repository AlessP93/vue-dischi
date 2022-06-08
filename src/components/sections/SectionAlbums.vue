<template>
  <section>
    <div class="container-lg py-5">
        <div class="row gap-4 justify-content-center">
            <CardAlbum class="col-12 col-sm-6 col-lg-2" v-for="(artist, index) in artists" :key="index" :card="artist"/>
         </div>
    </div>
 </section>
</template>

<script>
import axios from 'axios';
import CardAlbum from '../commons/CardAlbum.vue';

export default {
    name: 'SectionAlbums',
    data() {
        return {
            artists: [],
        }
    },
    components: {
    CardAlbum,
    },

    created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then((response) => {
        // handle success
        this.artists = response.data.response;
    
    })

    .catch((error) => {
        // handle error
        console.log(error);
    });
    }
}
</script>

<style lang="scss" scoped>

</style>