<template>
<div class="question-container">
    <div>
    <h1>Welcome to trivia!</h1>
    </div>
    <div>
    <button @click="getDataFromAPI" class="button">Next question</button>
    <p>{{ currentQuestion.question }}</p>
    <p>{{ currentQuestion.incorrect_answers }}</p>
    </div>
    <div>
    <button @click="unhideAnswer" class="button">answer</button>
    <p v-if="DisplayAnswer">{{ currentQuestion.correct_answer }}</p>
    <p v-else></p>
    
  </div>
</div>
</template>

<script>
import axios from 'axios'
export default{
    name: "quizQuestionAPI.vue",
    props: {

    },
    methods: {
    async getDataFromAPI() {
      this.DisplayAnswer = false;
      console.log("Getting more questions");
      try {
        const response = await axios.get('https://opentdb.com/api.php?amount=10&category=17&difficulty=easy&type=multiple');
        this.dataFromAPI = response.data.results;
        this.currentQuestion = this.dataFromAPI.shift()
        this.currentQuestion.incorrect_answers.push(this.currentQuestion.correct_answer);
        this.currentQuestion.incorrect_answers = this.currentQuestion.incorrect_answers
            .map(value => ({ value, sort: Math.random() }))
            .sort((a, b) => a.sort - b.sort)
            .map(({ value }) => value);
        console.log(this.currentQuestion)
      } catch (error) {
        console.error(error);
      }
    },
    unhideAnswer() {
      this.DisplayAnswer = true;
    }
    
  },
  data () {
    return {
      currentQuestion:'',
      DisplayAnswer: false,
      AvailableQuestions: []
    };
  }, 
}

</script>

<style scoped>
.question-container{
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 100px;
}
.button {
  color: white;
  background: #00a7e1;
  border-radius: 5px;
  border: 1px solid #2e6da4;
  padding: 5px;
  max-width: 200px;
  margin: 1px;
}
</style>