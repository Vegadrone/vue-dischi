<template>
  <main>
    <diskList/>
  </main>
</template>

<script> 
import diskList from "./diskList.vue";

export default {
 components: {
    diskList,
  },
}
</script>

<style lang="scss">
@import "../assets/styles/variables.scss";
main{
    padding:4.23rem
}
</style>