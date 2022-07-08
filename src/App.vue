<template>
  <div id="app">
    <MyHeader />

    <main>
      <DiscsList />
    </main>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import DiscsList from './components/DiscsList.vue';

export default {
  name: 'App',

  components: {
    MyHeader,
    DiscsList,
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
