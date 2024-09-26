<script setup>
const props = defineProps([
  'num1',
  'num2',
  'operacao',
  'atualizaNum1',
  'atualizaNum2',
  'atualizaOperacao',
]);
</script>

<template>
  <form>
    <div class="row">
      <div class="col-md-4 mb-3">
        <input
          :value="props.num1"
          @input="props.atualizaNum1"
          type="number"
          placeholder="Número 1"
          class="form-control shadow-sm border border-primary"
        />
      </div>

      <div class="col-md-4 mb-3">
        <input
          :value="props.num2"
          @input="props.atualizaNum2"
          type="number"
          placeholder="Número 2"
          class="form-control shadow-sm border border-primary"
        />
      </div>

      <div class="col-md-4 mb-3">
        <select
          @change="props.atualizaOperacao"
          class="form-control shadow-sm border border-primary"
          :value="props.operacao"
        >
          <option value="add">Adição</option>
          <option value="sub">Subtração</option>
          <option value="mul">Multiplicação</option>
          <option value="div">Divisão</option>
        </select>
      </div>
    </div>
  </form>
</template>
