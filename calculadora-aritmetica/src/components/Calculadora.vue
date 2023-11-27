<script setup>
const props = defineProps([
  'realizaCalculo'
])

</script>

<template>
  <div class="
    border 
    border-dark 
    d-flex 
    flex-row 
    justify-content-between 
    p-4
    rounded
  ">
    <input id="input-1" @keyup="realizaCalculo" type="number" value="0" class="form-control">
    <select
      id="select-form"
      @change="realizaCalculo"
      class="form-control text-center"
    >
      <option value="soma">+</option>
      <option value="subtracao">-</option>
      <option value="multiplicacao">x</option>
      <option value="divisao">/</option>
    </select>
    <input id="input-2" @keyup="realizaCalculo" type="number" value="0" class="form-control">
  </div>
</template>