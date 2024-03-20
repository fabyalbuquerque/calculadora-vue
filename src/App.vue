<script setup>
  import { reactive } from 'vue';
  import Calculadora from './components/Calculadora.vue';
  import Resultado from './components/Resultado.vue';

  const estado = reactive({
    number1: 0,
    number2: 0,

    operacao: 'add',
  })

  const firstNumber = event => {
    estado.number1 = parseFloat(event.target.value);
    console.log(estado.number1);
  }

  const secondNumber = event => {
    estado.number2 = parseFloat(event.target.value);
    console.log(estado.number2);
  }

  const selectOperacao = event => {
    estado.operacao = event.target.value;
    console.log(estado.operacao);
  }

  const calcular = () => {
    const { operacao } = estado;

    switch (operacao) {
    case 'add':
      return estado.number1 + estado.number2;
    case 'subtract':
      return estado.number1 - estado.number2;
    case 'multiply':
      return estado.number1 * estado.number2;
    case 'divide':
      if (estado.number2 === 0) {
        return "Erro: Divisão por zero";
      }
      return estado.number1 / estado.number2; 
    default:
      return "Operação inválida";
  }
  }

</script>

<template>
  <div class="container mt-5">
      <div class="row justify-content-center">
        <div class="col-md-6">
          <div class="card">
            <div class="card-header text-center">
              Calculadora Aritmética
            </div>
            <div class="card-body">
              <Calculadora :primeiro-campo="firstNumber" :segundo-campo="secondNumber" :seleciona-operacao="selectOperacao"/>
              <Resultado :calculater="calcular()"/>
            </div>
          </div>
        </div>
      </div>
  </div>
</template>

<style scoped>
  
</style>
