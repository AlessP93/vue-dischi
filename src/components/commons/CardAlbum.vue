<template>
  <div class="singleCard">
     <!-- <img :src="artists.poster" :alt="artists.title">
     <h3>{{artists.title}}</h3>
     <small>{{artists.author}}</small>
     <small>{{artists.year}}</small> -->

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

</style>