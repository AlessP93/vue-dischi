<template>
  <div class="row">
    ffff
    <form @submit.prevent="$emit('filterInput', selected)">
      <select v-model="selected">
          <option value="artist.genre" :v-for="(artist, index) in artists">{{artist.genre}}</option>
      </select>
    </form>
  </div>
</template>

<script>
export default {    
    name: 'InputSelect',
    props: {
      artists: []
    }
}
</script>

<style lang="scss" scoped>

</style>