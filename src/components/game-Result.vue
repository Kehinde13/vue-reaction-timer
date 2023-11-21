<template>
    <h3>Your reaction time is {{ score }}</h3>
    <P v-if="rank"> {{ rank }} </P>
</template>

<script>
  export default {
       props: ['score'],
       data(){
        return {
            rank: null
        }
       },
       mounted(){
        if(this.score < 250){
            this.rank = "Ninja Reflexes"
        } else if (this.score < 400){
            this.rank = "Rapid Reflexes"
        } else {
            this.rank = "Snail Reflexes"
        }
       }
  }
</script>

<style>
    h3, p{
        text-align: center;
    }
</style>