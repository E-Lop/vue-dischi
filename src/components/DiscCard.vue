<template>
  <div class="disc_card">
    <img :src="poster" :alt="title" />
    <h3 class="author">{{ author }}</h3>
    <div class="title">{{ title }}</div>
    <div class="genre">{{ genre }}</div>
    <div class="year">{{ year }}</div>
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
