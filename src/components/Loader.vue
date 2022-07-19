<template>
  <div class="d-flex justify-content-center">
    <div class="loader d-flex justify-content-center align-items-center">
    <h1 class="loader-text fw-bold text-light text-uppercase">loading</h1>
  </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
@import "../assets/styles/variables.scss";
    .loader{
        width: 100rem;
        height: 50rem;
        background-color: $cardBgColor;
    }


</style>