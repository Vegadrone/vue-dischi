<template>
  <div class="card-wrapper">
    <img :src="disk.poster" :alt="disk.title">
    <div class="card-text text-center">
      <h5 class="title text-light fw-bold">{{disk.title}}</h5>
      <span class="artist fw-bold">{{disk.author}}</span>
      <span class="year d-block">{{disk.year}}</span>
    </div>

  </div>
</template>

<script>


export default {
    props: ['disk']
}
</script>

<style lang="scss">
@import "../assets/styles/variables.scss";
 .card-wrapper{
    background-color: $cardBgColor;
 }

 .artist,
 .year{
  color: $cardTextColor;
 }
</style>