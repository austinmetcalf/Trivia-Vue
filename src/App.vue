<template>
  <div>
    
    Austin is great usually
    <button @click="getDataFromAPI">Get question</button>
    <p>{{ currentQuestion }}test</p>
  </div>
</template>

<script>

import axios from 'axios'

export default {
  name: 'App',
  // components: {
  //   quizQuestion,
  // },
  methods: {
    async getDataFromAPI() {
      try {
        const response = await axios.get('https://opentdb.com/api.php?amount=40&type=multiple');
        this.dataFromAPI = response.data;
      } catch (error) {
        console.error(error);
      }
    },
  },
  data () {
    return {
      currentQuestion:'',
    };
  }, 
}
</script>

<style>

</style>
