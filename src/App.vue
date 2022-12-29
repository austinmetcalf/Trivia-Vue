<template>
  <div>
    <div class="team">
      <input placeholder="Team Name">0
      <button>-</button>
      <button>+</button>
    </div>
    <div class="header-container">
      <h1>Welcome to trivia!</h1>
    </div>
    <div class="question-container">
      <button @click="getDataFromAPI">Next question</button>
      <p>{{ currentQuestion }}</p>
      <p>{{ currentQuestion.correct_answer }}</p>
      <p>{{ currentQuestion.incorrect_answers }}</p>
    </div>
    <QuizQuestion/>

    
    
    
  </div>
</template>

<script>

import axios from 'axios'
import QuizQuestion from './components/quizQuestion';

export default {
  name: 'App',
  components: {
    QuizQuestion,
  },
  methods: {
    async getDataFromAPI() {
      try {
        const response = await axios.get('https://opentdb.com/api.php?amount=40&type=multiple');
        this.dataFromAPI = response.data.results;
        this.currentQuestion = this.dataFromAPI.shift()
        console.log(this.dataFromAPI)
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
.header-container{
  display: flex;
  justify-content: center;
}
.question-container{
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
