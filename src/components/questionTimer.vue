<template>
  <div class="timer-display">
    <div>
      <div class="time-size">{{ countdown }}</div>
      <button @click="toggleCountdown" class="button cursor-pointer">
        {{ countdownStarted ? "Stop" : "Start" }} Time
      </button>
      <button @click="resetCountdown" class="button cursor-pointer">Reset Countdown</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "questionTimer",
  props: {},
  data() {
    return {
      countdown: 30,
      countdownStarted: false,
      intervalId: null,
    };
  },
  created() {
    // const intervalID= setInterval(()=> {
    //     this.countdown--
    //     if(this.countdown === 0){
    //         clearInterval(intervalID)
    //     }
    // },1000)
  },
  methods: {
    toggleCountdown() {
      this.countdownStarted = !this.countdownStarted;
      if (this.countdownStarted) {
        this.startCountdown();
      } else {
        this.stopCountdown();
      }
    },
    startCountdown() {
      this.intervalId = setInterval(() => {
        this.countdown--;
        if (this.countdown <= 0) {
          clearInterval(this.intervalId);
        }
      }, 1000);
    },
    stopCountdown() {
      clearInterval(this.intervalId);
    },
    resetCountdown() {
      this.countdown = 30
      clearInterval(this.intervalId)
      this.countdownStarted = false
    },
  },
};
</script>

<style scoped>
.timer-display {
  display: flex;
  justify-content: center;
  margin-top: 100px;
  
}
.time-size {
  font-size: 100px;
  justify-content: center;
  display: flex;
  color: red;
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
.cursor-pointer{
  cursor: pointer;
}
</style>
