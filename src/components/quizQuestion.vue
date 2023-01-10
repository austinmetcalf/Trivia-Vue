<template>
  <div class="question-container">
    <h1>Trivia Quiz</h1>
    <div class="question-container">
      <p>{{ currentQuestion.prompt }}</p>
      <button @click="toggleAnswer">{{ buttonText }}</button>
      <p v-if="currentQuestion.showAnswer">{{ currentQuestion.answer }}</p>
    </div>
    <button v-if="currentIndex < questions.length - 1" @click="nextQuestion">Next</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentIndex: 0,
      buttonText: 'Show Answer',
      questions: [
        {
          prompt: 'What is the capital of France?',
          answer: 'Paris',
          showAnswer: false
        },
        {
          prompt: 'What is the largest ocean in the world?',
          answer: 'Pacific Ocean',
          showAnswer: false
        }
      ]
    }
  },
  computed: {
    currentQuestion() {
      return this.questions[this.currentIndex]
    }
  },
  methods: {
    toggleAnswer() {
      this.currentQuestion.showAnswer = !this.currentQuestion.showAnswer
      this.buttonText = this.currentQuestion.showAnswer ? 'Hide Answer' : 'Show Answer'
    },
    nextQuestion() {
      this.currentIndex++
    }
  }
}
</script>

<style scoped>
.question-container{
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>