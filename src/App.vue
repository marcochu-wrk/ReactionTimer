<template>
  <h1>Reaction Timer Game</h1>
  <button @click="start" :disabled="isPlaying">Start</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <Results v-if="showResults" :showResult="score"/>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'
export default {
  name: 'App',
  components: {
    Block,
    Results
  },
  data(){
    return{
      isPlaying: false,
      delay: null,
      score:0,
      showResults: false
    }
  },
  methods:{
    start(){
      this.isPlaying = true
      this.showResults = false
      this.delay = 2000 + Math.random()*5000
    },
    endGame(reactionTime){
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button{
  padding: 1rem;
  background: turquoise;
  color: white;
  text-align: center;
 
}

</style>
