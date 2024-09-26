<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

const estado = reactive({
  num1: 0,
  num2: 0,
  operacao: 'add',
});

const calculaResultado = () => {
  const { num1, num2, operacao } = estado;

  switch (operacao) {
    case 'add':
      return num1 + num2;
    case 'sub':
      return num1 - num2;
    case 'mul':
      return num1 * num2;
    case 'div':
      return num2 !== 0 ? num1 / num2 : 'Erro: Divisão por zero';
    default:
      return 0;
  }
};
</script>

<template>
  <div class="container">
    <Cabecalho />
    <Formulario
      :num1="estado.num1"
      :num2="estado.num2"
      :operacao="estado.operacao"
      :atualiza-num1="evento => (estado.num1 = parseFloat(evento.target.value))"
      :atualiza-num2="evento => (estado.num2 = parseFloat(evento.target.value))"
      :atualiza-operacao="evento => (estado.operacao = evento.target.value)"
    />
    <Resultado :resultado="calculaResultado()" />
  </div>
</template>
