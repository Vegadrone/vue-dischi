<template>
  <div class="container">
    <div class="row">
      <div class="col-4">
        <selectGenre :genres="genres" />
      </div>
    </div>
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
import selectGenre from "./selectGenre.vue";

export default {
  data: function () {
    return {
      disks: [],
      genres: [],
    };
  },
  components: {
    diskCard,
    Loader,
    selectGenre,
  },
  methods: {
    getDiskInfo() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((result) => {
          this.disks = result.data.response;
          this.disks.forEach((element) => {
            if(!this.genres.includes(element.genre)){
              this.genres.push(element.genre);
            }
          });
          console.log(this.disks);
          console.log(this.genres);
        })
        .catch((error) => {
          console.warn(error);
        });
    },
  },

  created() {
    this.getDiskInfo();
  },
};
</script>

<style lang="scss">
@import "../assets/styles/variables.scss";
diskCard {
  margin: 0 auto;
}
</style>