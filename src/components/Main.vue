<template>
  <main>
    <h1>MAIN</h1>
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
}


</style>