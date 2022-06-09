<template>
  <div class="row">
    <form>
        <select v-model="selected" @change="$emit('changeSelectGenre', selected)">
          <!-- <option :value="artist.genre" v-for="(artist, index) in artists" :key="index">{{artist.genre}}</option> -->
          <option value="" selected>All</option>
          <option value="Rock">Rock</option>
          <option value="Metal">Metal</option>
          <option value="Pop">Pop</option>
          <option value="Jazz">Jazz</option>
        </select>
      <button type="submit">search</button>
    </form>
  </div>
</template>

<script>
export default {    
    name: 'InputSelect',
    data() {
      return {
        selected: "",
        // genre: [],
      }
    },
    // props: {
    //   artists: Object,
    // }
  
}
</script>

<style lang="scss" scoped>

</style>