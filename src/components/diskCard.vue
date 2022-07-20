<template>
  <div class="card-wrapper">
    <div class="img-container">
      <img :src="disk.poster" :alt="disk.title" />
    </div>
    <div class="card-text text-center">
      <h5 class="title text-light fw-bold mt-3 text-uppercase">{{ disk.title }}</h5>
      <span class="artist fw-bold">{{ disk.author }}</span>
      <span class="year d-block">{{ disk.year }}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["disk"],
};
</script>

<style lang="scss">
@import "../assets/styles/variables.scss";
.card-wrapper {
  background-color: $cardBgColor;
  height: 21rem;
  padding: 2rem;
  border-radius: 5px;
  margin: 1rem 1rem;

  .img-container {
    width: 10rem;
    height: 10rem;
      img{
        width: 100%;
        margin-left: 1.15rem; //temporary fix
      }
  }
}

.artist,
.year {
  color: $cardTextColor;
}
</style>