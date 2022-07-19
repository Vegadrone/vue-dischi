<template>
  <div class="container">
    <Loader v-if="disks.length != 10" />
    <div class="row justify-content-between" v-show="disks.length <= 10">
      <diskCard 
        class="col-2"
        v-for="(disk, index) in disks"
        :key="index"
        :disk="disk"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import diskCard from "./diskCard.vue";
import Loader from "./Loader.vue";

export default {
  data: function () {
    return {
      disks: [],
    };
  },
  components: {
    diskCard,
    Loader
  },
  methods: {
    getDisk() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((result) => {
          this.disks = result.data.response;
          console.log(this.disks);
        })
        .catch((error) => {
          console.warn(error);
        });
    },
  },

  created() {
    this.getDisk();
  },
};
</script>

<style lang="scss">
@import "../assets/styles/variables.scss";
  diskCard{
    margin: 0 auto;
  }
</style>