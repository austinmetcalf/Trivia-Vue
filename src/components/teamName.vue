<template>
<div class="team-container">
   <!-- <div class="team-container"> -->
            <input class="spacer" placeholder="Team Name">
            <div class="team-score">{{ score }}</div>
            <button class="button" @click="decrementScore">-</button>
            <button class="button" @click="incrementScore">+</button>
    
    <!-- </div>  -->
</div>
</template>
  
<script>
  
  export default {
    name: 'teamName.vue',
    props:{

    },
    data(){
        return{
            score: 0
        }
    },
    methods:{
        incrementScore(){
            this.score++
        },
        decrementScore(){
            this.score--
        }
    }

  }

</script>

<style scoped>
.button{
    color: white;
    background: #00a7e1;
    border-radius: 5px;
    border: 1px solid #2e6da4;
    padding: 5px;
    max-width: 200px;
    margin: 1px;
}
.team-container{
    display: flex;
}

.spacer{
    margin: 3px;
}
.team-score{
    
    margin: 2px;
}
</style>