<template>
  <div>
    <select class="form-select" aria-label="Default select example">
      <option selected>Scegli un genere</option>
      <option v-for="(genre, index) in genres" :key="index" value="genre">{{genre}}</option>
    </select>
  </div>
</template>

<script>
export default {
 props: ["genres"]
};
</script>

<style>
</style>