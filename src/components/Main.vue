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
    background-color: $bgColor;
    padding:5rem
}
</style>