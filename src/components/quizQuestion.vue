<template>
    <div>
      
     
    </div>
  </template>
  
  <script>
  import axios from 'axios';
 
  export default {
    data() {
      return {
        questions: []
      }
    },
    created() {
      axios.get('https://opentdb.com/api.php?amount=40&type=multiple')
        .then(response => {
          this.questions = response.data.results;
        })
        .catch(error => {
          console.error(error);
        });
    }
  }
  </script>
  