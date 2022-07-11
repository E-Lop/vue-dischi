<template>
  <div class="container">
    <div v-if="isLoaded" class="discs_list">
      <DiscFilters :value="genreArray" />
      <DiscCard
        v-for="(disc, index) in discsArray"
        :key="index"
        :author="disc.author"
        :poster="disc.poster"
        :title="disc.title"
        :year="disc.year"
      />
    </div>
    <MyLoader v-else />
  </div>
</template>

<script>
import DiscCard from './DiscCard.vue';
import MyLoader from './MyLoader.vue';
import DiscFilters from './DiscFilters.vue';
import axios from 'axios';

export default {
  name: 'DiscsList',
  data() {
    return {
      // array contenente i dati sui dischi presi tramite API
      discsArray: [],
      // array che contiene i generi musicali
      genreArray: [],
      isLoaded: false,
    };
  },
  methods: {
    // inserisce i generi musicali nell'array senza doppioni
    extractGenres() {
      this.discsArray.forEach((element) => {
        if (!this.genreArray.includes(element.genre)) {
          this.genreArray.push(element.genre);
        }
      });
    },
  },
  mounted() {
    axios
      .get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((response) => {
        const singleDisc = response.data.response;
        this.discsArray = singleDisc;
        this.isLoaded = true;
        this.extractGenres(this.discsArray);
      })
      .catch((err) => {
        console.log('Error', err);
      });
  },

  components: {
    DiscCard,
    MyLoader,
    DiscFilters,
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
