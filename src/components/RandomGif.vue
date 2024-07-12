<template>
  <div class="max-w-5xl mx-auto text-center" v-if="gifUrl">
    <img :src="gifUrl" alt="Random Gif" class="mx-auto"/>
  </div>
  <div class="max-w-5xl mx-auto text-center" v-else>
    <iframe src="https://giphy.com/embed/917Ve5cLpoB3Nhd1xh" width="480" height="400" frameBorder="0"
            class="giphy-embed max-w-5xl mx-auto" allowFullScreen></iframe>
  </div>
</template>

<script>
import axios from 'axios';
import { GIPHY_API_KEY } from '../../config';

export default {
  data() {
    return {
      gifUrl: '',
      searchTerm: 'the-office',
    };
  },
  created() {
    this.fetchRandomGif();
  },
  methods: {
    async fetchRandomGif() {
      try {
        const response = await axios.get('https://api.giphy.com/v1/gifs/random', {
          params: {
            api_key: GIPHY_API_KEY,
            tag: this.searchTerm,
            rating: 'g',
          },
        });
        this.gifUrl = response.data.data.images.original.url;
      } catch (error) {
        console.error('Error fetching random gif:', error);
      }
    },
  },
};
</script>

<style scoped>
div {
  text-align: center;
}

img {
  max-width: 100%;
  height: auto;
}
</style>
