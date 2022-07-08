<template>
  <div id="app">
    <MyHeader />

    <main>
      <div>
        {{ discsArray }}
      </div>
    </main>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import axios from 'axios';

export default {
  name: 'App',
  data() {
    return {
      // array contenente i dati sui dischi presi tramite API
      discsArray: '',
    };
  },
  methods: {},
  mounted() {
    axios
      .get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((response) => {
        const singleDisc = response.data.response;
        this.discsArray = singleDisc;
      });
  },
  components: {
    MyHeader,
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
