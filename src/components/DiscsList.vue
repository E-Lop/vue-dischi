<template>
  <div class="container">
    <div class="discs_list">
      <DiscCard
        v-for="(disc, index) in discsArray"
        :key="index"
        :author="disc.author"
        :genre="disc.genre"
        :poster="disc.poster"
        :title="disc.title"
        :year="disc.year"
      />
    </div>
  </div>
</template>

<script>
import DiscCard from './DiscCard.vue';
import axios from 'axios';

export default {
  name: 'DiscsList',
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
      });
  },
  components: {
    DiscCard,
  },
};
</script>

<style lang="scss" scoped>
.discs_list {
  width: 100%;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 20px;
}
</style>
