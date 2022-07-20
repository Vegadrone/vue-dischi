<template>
  <div>
    <select
      v-model="inputSelection"
      @change="$emit('select', inputSelection)"
      class="form-select"
      aria-label="Default select example"
    >
      <option selected>Scegli un genere</option>
      <option v-for="(genre, index) in genres" :key="index" :value="genre">
        {{ genre }}
      </option>
    </select>
    <h4 class="text-light">{{inputSelection}}</h4>
  </div>
</template>

<script>
export default {
  props: ["genres"],

  data() {
    return {
      inputSelection: "",
    };
  },
};
</script>

<style>
</style>