<template>
  <div>
    <div class="team-name-header">
      <teamName> </teamName>

      <teamName> </teamName>
      <teamName> </teamName>
      <teamName> </teamName>
    </div>

    <hr />
    <div class="quiz-container">
      <QuizQuestionAPI></QuizQuestionAPI>
    </div>

    <!-- <QuizQuestion/> -->
    <hr />
    <questionTimer></questionTimer>
    <div class="copy-right">&copy; Austin Metcalf</div>
  </div>
</template>

<script>
import teamName from "./components/teamName.vue";
import questionTimer from "./components/questionTimer.vue";
import QuizQuestionAPI from "./components/quizQuestionAPI.vue";
// import quizQuestionVue from './components/quizQuestion.vue';

export default {
  name: "App",
  components: {
    teamName,
    questionTimer,
    QuizQuestionAPI,
    // quizQuestionVue
  },
};
</script>

<style scoped>
.team-name-header {
  display: flex;
  margin-bottom: 15px;
}
.quiz-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.copy-right {
  position: fixed;
  bottom: 0;
  right: 0;
}
</style>
