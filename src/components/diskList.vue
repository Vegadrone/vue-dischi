<template>
  <div class="container">
    <div class="row d-flex flex-wrap">
      <diskCard
        class="col"
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
  width: calc(100% / 5);
}
</style>