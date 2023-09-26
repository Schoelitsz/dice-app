<template>
    <div class="dicebutton">
        <h1>Roll me!</h1>
      <button @click="rollDice">Roll</button>
      <p v-if="result !== null">You rolled: {{ result }}</p>
    </div>
</template>
  
  <script setup>
  import { ref } from 'vue';
  
  const msg = defineProps({
    type: String,
    required: true
  });
  
  const result = ref(null);
  
  const rollDice = () => {
    result.value = Math.floor(Math.random() * 6) + 1;
  };
  </script>
  
  <style scoped>

    body {
        background-color: aqua;
    }
  h1 {
    font-weight: 500;
    font-size: 2.6rem;
    position: relative;
    top: -10px;
  }
  
  button {
    margin-top: 100px;
    padding: 5px 30px;
    cursor: pointer;
  }
  
  h3 {
    font-size: 1.2rem;
  }
  
  .greetings h1,
  .greetings h3 {
    text-align: center;
  }
  
  @media (min-width: 1024px) {
    .greetings h1,
    .greetings h3 {
      text-align: left;
    }
  }
  </style>
  