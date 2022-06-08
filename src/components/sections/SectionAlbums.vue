<template>
  <section>
    <div class="container-lg py-5">
     
            <InputSelect :artists="artists"/>

        <div class="row gap-4 justify-content-center">
            <CardAlbum class="col-12 col-sm-6 col-lg-2" v-for="(artist, index) in artists" :key="index" :card="artist"/>
         </div>
    </div>
 </section>
</template>

<script>
import axios from 'axios';
import CardAlbum from '../commons/CardAlbum.vue';
import InputSelect from '../commons/InputSelect.vue';

export default {
    name: 'SectionAlbums',
    data() {
        return {
            artists: [],
            genreFiltered: [],
        }
    },
    components: {
    CardAlbum,
    InputSelect,
    },

   methods: {
        filterInput(selected) {
            this.genreFiltered = this.artists.filter((elm) => { 
      
             return elm.genre.toLowerCase().includes(selected.toLowerCase());
            });
        }
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