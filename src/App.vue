<template>
  <div>HelloWorld</div>
</template>

<script>


export default {
  name: 'App',

  data(){
    return{
      question: undefined,
      incorrectAnswer:undefined,
      correctAnswer:undefined
    }
  },

  created(){
    this.axios
    .get('https://opentdb.com/api.php?amount=1&category=18')
    .then((response) => {
      this.question = response.data.results[0].question;
      this.incorrectAnswer = response.data.results[0].incorrect_answer;
      this.correctAnswer = response.data.results[0].correct_answer;
      
    })
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
