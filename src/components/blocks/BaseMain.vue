<template>
    <main>
        <SectionAlbums/>
    </main>
</template>

<script>
import SectionAlbums from '../sections/SectionAlbums.vue';

export default {
    name: 'BaseMain',
    components: {
        SectionAlbums
    },
}
</script>

<style lang="scss" scoped>
    main {
        background-color: var(--secondary-color);
        height: 100vh;
    }
</style>