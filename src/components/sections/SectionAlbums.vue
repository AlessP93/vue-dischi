<template>
  <section>
    <div class="container-lg py-5">
        <InputSelect :artists="artists" @changeSelectGenre='saveSelected'/>
        <div class="row gap-4 justify-content-center">
            <CardAlbum class="col-12 col-sm-6 col-lg-2" v-for="(artist, index) in filterInput" :key="index" :card="artist"/> 
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
            genreSave: "",
        }
    },
    components: {
    CardAlbum,
    InputSelect,
    },

   methods: {
        saveSelected(selected) {
            // console.log(selected);
            this.genreSave = selected;

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
    },
    computed: {
         filterInput() {
            if(this.genreSave === "" ) {
                return this.artists;
            } else {
                return this.artists.filter((elm) => { 
                    return elm.genre == this.genreSave;
                });
            }
        }
    }
    
}
</script>

<style lang="scss" scoped>

</style>