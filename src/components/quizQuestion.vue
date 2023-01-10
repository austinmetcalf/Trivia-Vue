<template>
  <div class="question-container">
    <h1>Welcome to Trivia!</h1>
    <p>Question {{ currentCount }} of {{ questions.length }}</p>
    <div class="question-container">
      <p>{{ currentQuestion.prompt }}</p>
      <button @click="toggleAnswer" class="button">{{ buttonText }}</button>
      <p v-if="currentQuestion.showAnswer">{{ currentQuestion.answer }}</p>
    </div>
    <button v-if="currentIndex < questions.length - 1" @click="nextQuestion" class="button">Next Question</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentIndex: 0,
      currentCount: 1,
      buttonText: 'Show Answer',
      questions: [
        {
          prompt: 'St Andrew cross, St George cross and St Patrick cross make up this flag -',
          answer: 'Union Jack or flag of United Kingdom',
          showAnswer: false
        },
        {
          prompt: 'In 2022 what viral online game did the New York Times purchase?',
          answer: 'Wordle',
          showAnswer: false
        },
        {
          prompt: 'What is the spanish word for donkey?',
          answer: 'Burro',
          showAnswer: false
        },
        {
          prompt: 'What is the largest ocean in the world?',
          answer: 'Pacific Ocean',
          showAnswer: false
        },
        {
          prompt: 'What is the largest ocean in the world?',
          answer: 'Pacific Ocean',
          showAnswer: false
        },
        {
          prompt: 'Which Kardashian got married in May 2022?  Who did she marry?',
          answer: 'Kourtney Kardashian to Travis Barker',
          showAnswer: false
        },
        {
          prompt: 'What is the largest ocean in the world?',
          answer: 'Pacific Ocean',
          showAnswer: false
        },
        {
          prompt: 'In 2022 Liz Truss won the office of Prime Minister.  How long did she serve before resigning?',
          answer: '45 days',
          showAnswer: false
        },
        {
          prompt: 'How many time zones does China have?',
          answer: 'One, declared by the CCP in 1949',
          showAnswer: false
        },
        {
          prompt: 'I was released in 1985, but in 2022 I increased in streams >9,000%.  What song am I? ',
          answer: 'Running up that hill',
          showAnswer: false
        },
        {
          prompt: 'What is the largest ocean in the world?',
          answer: 'Pacific Ocean',
          showAnswer: false
        },
        {
          prompt: 'What is the largest ocean in the world?',
          answer: 'Pacific Ocean',
          showAnswer: false
        },
        {
          prompt: 'Who is depicted on the US $100 bill?',
          answer: 'Ben Franklin',
          showAnswer: false
        },
        {
          prompt: 'What is the largest ocean in the world?',
          answer: 'Pacific Ocean',
          showAnswer: false
        },
        {
          prompt: 'What is the largest ocean in the world?',
          answer: 'Pacific Ocean',
          showAnswer: false
        },
        {
          prompt: 'What is the largest ocean in the world?',
          answer: 'Pacific Ocean',
          showAnswer: false
        },
        {
          prompt: 'Who purchased Twitter in 2022 for the price tag of $44 billion?',
          answer: 'Elon Musk',
          showAnswer: false
        },
        {
          prompt: 'What is the largest ocean in the world?',
          answer: 'Pacific Ocean',
          showAnswer: false
        },
        {
          prompt: 'What is the largest ocean in the world?',
          answer: 'Pacific Ocean',
          showAnswer: false
        },
        {
          prompt: 'What is the largest ocean in the world?',
          answer: 'Pacific Ocean',
          showAnswer: false
        },
        {
          prompt: 'What is the largest ocean in the world?',
          answer: 'Pacific Ocean',
          showAnswer: false
        },
        {
          prompt: 'What is the largest ocean in the world?',
          answer: 'Pacific Ocean',
          showAnswer: false
        },
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
      this.currentCount++
    }
  }
}
</script>

<style scoped>
.question-container{
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 25px;
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