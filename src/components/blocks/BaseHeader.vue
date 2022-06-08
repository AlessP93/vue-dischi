<template>
  <header>
    <div class="container-fluid">
        <img src="../../assets/img/spotify-logo.png" alt="logo-header">
    </div>
  </header>
</template>

<script>
export default {
    name: 'BaseHeader'
}   
</script>

<style lang="scss" scoped>
    .container-fluid {
        background-color: var(--primary-color);
        padding: .625rem;

        img {
            width: 5%;
        }
    }
</style>
