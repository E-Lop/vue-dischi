<template>
  <div class="disc_card">
    <img :src="poster" :alt="title" />
    <h3 class="title">{{ title }}</h3>
    <div class="minor_data">
      <div class="author">{{ author }}</div>
      <div class="year">{{ year }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DiscCard',
  props: {
    author: String,
    genre: String,
    poster: String,
    title: String,
    year: String,
  },
};
</script>

<style lang="scss">
@import '../style/common';
@import '../style/variables';

.disc_box {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.disc_card {
  width: calc((100% / 5) - 20px);
  min-width: 100px;
  padding: 10px;

  background-color: $main_color;
  div {
    text-align: center;
  }
}
h3 {
  font-size: 1.5rem;
  font-weight: bold;
  text-align: center;
  color: white;
  padding-top: 10px;
}
.minor_data {
  padding-top: 10px;
  color: #7e7667;
}
</style>
