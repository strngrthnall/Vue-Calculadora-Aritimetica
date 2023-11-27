<script setup>
const props = defineProps([
  'carregaResultado'
])

</script>

<template>
  <div class="
    container 
    d-flex 
    flex-column 
    text-center
    mt-3
  ">
    <h2>O resultado é:</h2>
    <h1>{{ props.carregaResultado }}</h1>
    
  </div>
</template>