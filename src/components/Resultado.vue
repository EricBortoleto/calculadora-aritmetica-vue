<script setup>
const props = defineProps(['resultado']);
</script>

<template>
  <div class="mt-4 text-center">
    <div class="p-4 border border-primary rounded shadow-sm bg-light">
      <h2 class="text-primary">Resultado: {{ props.resultado }}</h2>
    </div>
  </div>
</template>
