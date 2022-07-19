<template>
  <div>
    <h3>disk List</h3>
    <diskCard />
  </div>
</template>

<script>
import diskCard from "./diskCard.vue";

export default {
 components: {
    diskCard,
  },
}
</script>

<style lang="scss">
@import "../assets/styles/variables.scss";

</style>