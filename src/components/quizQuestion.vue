<template>
  <div class="question-container-1">
    <h3 class="videos">Videos</h3>
    <a :href="link" class="videos">{{ linkText }}</a>
    <h1>Welcome to Trivia! The future is now!</h1>
    <p>Question {{ currentCount }} of {{ questions.length }}</p>
    <div class="question-container-2">
      <p>{{ currentQuestion.prompt }}</p>
      <button @click="toggleAnswer" class="button cursor-pointer">{{ buttonText }}</button>
      <p v-if="currentQuestion.showAnswer">{{ currentQuestion.answer }}</p>
    </div>
    <button v-if="currentIndex < questions.length - 1" @click="nextQuestion" class="button cursor-pointer">Next Question</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentIndex: 0,
      currentCount: 1,
      buttonText: 'Show Answer',
      link: 'https://www.youtube.com/watch?v=i2gNx4-REIA',
      linkText: 'Chill',
      questions: [
        {
          prompt: 'According to an average of multiple cybersecurtiy firms, what percentage of internet traffice is non-human',
          answer: '40%',
          showAnswer: false
        },
        {
          prompt: 'In 2022 what viral online game did the New York Times purchase?',
          answer: 'Wordle',
          showAnswer: false
        },
        {
          prompt: 'With over 500 million, who has the most followers on instagram in 2023?',
          answer: 'Cristiano Ronaldo',
          showAnswer: false
        },
        {
          prompt: 'Is the following expression syntatically correct: 3 === 3',
          answer: 'True',
          showAnswer: false
        },
        {
          prompt: 'Who holds the NBA scoring record?',
          answer: 'Kareem Abdul-Jabbar',
          showAnswer: false
        },
        {
          prompt: 'Which Kardashian got married in May 2022?  Who did she marry?',
          answer: 'Kourtney Kardashian to Travis Barker',
          showAnswer: false
        },
        {
          prompt: 'At the 2022 Berlin marathon, Kipchoge set a new world record.  At a pace of 13mph, what was his finish time?',
          answer: '2:01:09',
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
          prompt: 'I was released in 1985, but in 2022 my Spotify streams increased 9,000%.  What song am I? ',
          answer: 'Running up that hill',
          showAnswer: false
        },
        {
          prompt: 'Name all countries that border France',
          answer: 'Italy, Switzerland, Germany, Luxembourg, Belgium, Andorra, Spain and Monaco',
          showAnswer: false
        },
        {
          prompt: 'In the early hours of January 7th, 2022, the House elected a new Speaker.  Who is it?',
          answer: 'Kevin McCarthy',
          showAnswer: false
        },
        {
          prompt: 'Who is depicted on the US $100 bill?',
          answer: 'Ben Franklin',
          showAnswer: false
        },
        {
          prompt: 'Who is the author of the Star-Spangled Banner?',
          answer: 'Francis Scott Key',
          showAnswer: false
        },
        {
          prompt: 'If data is a collection of facts and/ or statistics.  What is the word for a single fact or statistic?',
          answer: 'datum',
          showAnswer: false
        },
        {
          prompt: 'Re-write the following Ebonics into English: No cap, this meal was straight bussin fr fr',
          answer: 'I wont lie, this meal was very good',
          showAnswer: false
        },
        {
          prompt: 'Who purchased Twitter in 2022 for the price tag of $44 billion?',
          answer: 'Elon Musk',
          showAnswer: false
        },
        {
          prompt: 'On January 1st, 2022, Brazil swore in a new President.  Who was it?',
          answer: 'Luiz Inacio Lula da Silva',
          showAnswer: false
        },
        {
          prompt: 'What was the name of the high school in Grease?',
          answer: 'Rydell High',
          showAnswer: false
        },
        {
          prompt: 'Complete the response in this viral video:',
          answer: 'What the hell is even that?',
          showAnswer: false
        },
        {
          prompt: 'Which city sits lowest in latitude: San Diego, Tucson, or Austin?',
          answer: 'Austin',
          showAnswer: false
        },
        {
          prompt: 'What does HTML stand for? ',
          answer: 'HyperText Markup Language',
          showAnswer: false
        },
        {
          prompt: 'In which year was the first iPhone released?',
          answer: '2007',
          showAnswer: false
        },
        {
          prompt: 'What is the longest running Broadway show?',
          answer: 'Phantom of the Opera',
          showAnswer: false
        },
        {
          prompt: 'In Greek mythology, who was known to be the messenger of the gods?',
          answer: 'Hermes',
          showAnswer: false
        },
        {
          prompt: 'In what city was the first Covid-19 infection discovered?',
          answer: 'Wuhan, China',
          showAnswer: false
        },
        {
          prompt: 'The winter solstice occurs on which day of the year?',
          answer: 'December 21st',
          showAnswer: false
        },
        {
          prompt: 'What is the rarest blood type?',
          answer: 'AB negative',
          showAnswer: false
        },
        {
          prompt: 'What alcoholic beverage is made from juniper berries?',
          answer: 'Gin',
          showAnswer: false
        },
        {
          prompt: 'Where on the food pyramid do eggplants belong?',
          answer: 'fruits section',
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
.question-container-1{
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 25px;
  margin-bottom: 50px;
}
.question-container-2{
  display: flex;
  flex-direction: column;
  align-items: center;
  font-size: x-large;
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
.videos{
  position: relative;
  left: 400px;
}
h3{
  text-decoration: underline;
}
.cursor-pointer{
  cursor: pointer;
}
</style>