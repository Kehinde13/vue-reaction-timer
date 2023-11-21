<script setup>
 import Block from './components/game-Block.vue'
 import Result from './components/Result.vue';
</script>

<template>
   <div class="main">
        <h1>Reaction Timer</h1>
        <button @click="start" :disabled="isPlaying">play</button>
   </div>
   <Block :delay="delay" v-if="isPlaying" @end="endGame"/>
   <Result :score="score" v-if="score"/>
</template>

<script>
  export default {
    name: 'app',
    data (){
     return {
        isPlaying: false,
        delay: null,
        score: null,
    }
    },
    methods: {
        start() {
        this.delay = 2000 + Math.random() * 5000
        this.isPlaying = true
        this.score= null
        },

        endGame(reaction){
          this.score = reaction
          this.isPlaying = false
        }
    }
  }
</script>


<style>
     .main {
        width: 100%;
        height: 100%;
        text-align: center;
        margin: 100px auto;
     }
</style>