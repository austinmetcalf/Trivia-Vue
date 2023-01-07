<template>
  <div>
    <h1>Trivia Game</h1>
    <div v-for="(question, index) in questions" :key="index">
      <p>{{ question.text }}</p>
      <form @submit.prevent="checkAnswer(question)">
        <input type="text" v-model="userAnswer" />
        <button type="submit">Submit</button>
      </form>
      <p v-if="question.correct">Correct!</p>
      <p v-else>Incorrect. Try again.</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "quizQuestion",
  props:{},
  data() {
    return {
      questions: [
        { text: 'What is the capital of France?', answer: 'Paris', correct: null },
        { text: 'What is the largest ocean on Earth?', answer: 'Pacific Ocean', correct: null }
      ],
      userAnswer: ''
    }
  },
  computed: {
    currentQuestion() {
      return this.questions.findIndex(q => q.correct === null) + 1;
    }
  },
  methods: {
    checkAnswer(question) {
      if (this.userAnswer.toLowerCase() === question.answer.toLowerCase()) {
        question.correct = true;
      } else {
        question.correct = false;
      }
      this.userAnswer = '';
    }
  }
}
</script>


<style scoped>
</style>