<template>
  <question-box
    v-for="question in questions"
    v-bind:question="question"
    v-on:choice-made="choiceMade"
    ></question-box>
  <h2>You would rather...</h2>
  <li v-for="answer in answers">Have {{ answer }}</li>
</template>

<script>
import QuestionBox from './components/WouldYouRatherQuestion.vue'

export default {
  name: 'App',
  components: {QuestionBox,},
  data() {
    return {
      questions: [
        {
          id:0,
          q:"Would you rather have orangutang arms or ostrich legs?",
          a1:"Orangutang arms",
          a2:"Ostrich Legs"
        },
        {
          id:1,
          q:"Would you rather have an anteater tongue or elephant ears?",
          a1:"Anteater tongue",
          a2:"Elephant ears"
        },
        {
          id:2,
          q:"Would you rather take 5 dollars now or 20 dollars in 2 months?",
          a1:"5 dollars now",
          a2:"20 dollars in the future"
        }
      ],
      answers: [],
    }
  },
  methods: {
    choiceMade(question, answer) {
      this.answers[question]=answer
    }
  }
}
</script>

<style>
body {
  background: navy;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: purple;
  margin-top: 60px;
  background: aquamarine
}
</style>

