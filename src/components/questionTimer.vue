<template>
<div class="timer-display">
    <div>       
    <div class="time-size">{{ countdown }}</div>
    <button class="button" @click="resetTimer">Reset Time</button>
    <button @click="pauseTimer" class="button">Pause Time</button>
    </div>
</div>
</template>

<script>

    export default {
        name: "questionTimer",
        props: {

        },
        data(){
            return {
                countdown: 30,
                intervalID: null
            }
        },
        created(){
            const intervalID= setInterval(()=> {
                this.countdown--
                if(this.countdown === 0){
                    clearInterval(intervalID)
                
                }
            },1000)
            
        },
        methods: {
            resetTimer() {
             clearInterval(this.intervalId)
            this.countdown = 30
             this.intervalId = setInterval(() => {
             this.countdown--
            if (this.countdown === 0) {
            clearInterval(this.intervalId)
             }
            }, 1000)
            },
            pauseTimer() {
            clearInterval(this.intervalId)
            this.intervalId = null
            },
        }
    }
</script>

<style>
.timer-display{
    display: flex;
    justify-content: center;
    margin-top: 100px;
}
.time-size{
    font-size: 100px;
    justify-content: center;
    display: flex;
    color: red;
}
.button{
    color: white;
    background: #00a7e1;
    border-radius: 5px;
    border: 1px solid #2e6da4;
    padding: 5px;
    max-width: 200px;
    margin: 1px;
}
</style>