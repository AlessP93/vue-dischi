<template>
  <div class="row">
    <select id="select-genre"  @submit.prevent="$emit('selected)">
        <option value=""></option>
    </select>
  </div>
</template>

<script>
export default {    
    name: 'InputSelect'
}
</script>

<style>

</style>