<template>
  <div id="app">
    <MyHeader />

    <main>
      <DiscCard
        v-for="(disc, index) in discsArray"
        :key="index"
        :author="disc.author"
        :genre="disc.genre"
        :poster="disc.poster"
        :title="disc.title"
        :year="disc.year"
      />
    </main>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import DiscCard from './components/DiscCard.vue';
import axios from 'axios';

export default {
  name: 'App',
  data() {
    return {
      // array contenente i dati sui dischi presi tramite API
      discsArray: [],
    };
  },
  methods: {},
  mounted() {
    axios
      .get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((response) => {
        const singleDisc = response.data.response;
        this.discsArray = singleDisc;
        console.log('array', this.discsArray);
      });
  },
  components: {
    MyHeader,
    DiscCard,
  },
};
</script>

<style lang="scss">
@import './style/common';
@import './style/variables';

main {
  background-color: #1e2d3b;
  padding-top: 50px;
  padding-bottom: 50px;
}
</style>
