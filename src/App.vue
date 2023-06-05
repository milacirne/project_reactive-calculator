<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Operation from './components/Operation.vue';
import Result from './components/Result.vue';

  const state = reactive({
    operation: '+',
    number1: '',
    number2: ''
  });

  const result = () => {
    const {operation} = state;
    switch(operation) {
      case '-':
        return parseFloat(state.number1) - parseFloat(state.number2);
      case '*':
        return parseFloat(state.number1) * parseFloat(state.number2);
      case '/':
        return parseFloat(state.number1) / parseFloat(state.number2);
      default:
      return parseFloat(state.number1) + parseFloat(state.number2);
    };
  };

</script>

<template>
  <body>
    <div class="container">
      <Cabecalho />
      <Operation :operation="event => state.operation = event.target.value" :number1="event => state.number1 = event.target.value" :number2="event => state.number2 = event.target.value"></Operation>
      <Result :number1="state.number1" :number2="state.number2" :result="result()" />
    </div>
  </body>
</template>

<style scoped>
  * {
    margin: 0 auto;
    padding: 0 auto;
    box-sizing: border-box;
    font-family: sans-serif;
  }

  .container {
    margin: 0 auto;
    text-align: center;
    background-color: rgb(81, 123, 142);
  }
</style>
