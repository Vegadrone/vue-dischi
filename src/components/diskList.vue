<template>
  <div>
    <h3>disk List</h3>
    <diskCard />
  </div>
</template>

<script>
import axios from "axios";
import diskCard from "./diskCard.vue";

export default {
  data: function () {
    return {
        disks: [],
    };
  },
  components: {
    diskCard,
  },
  methods: {
    getDisk() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((result)=>{
            console.log(result.data.response)
            this.disks.push(result.data.response)
        })
        .catch((error)=>{
            console.warn(error)

        })
    },
  },
    
  created() {
    this.getDisk();
  },
};
</script>

<style lang="scss">
@import "../assets/styles/variables.scss";
</style>