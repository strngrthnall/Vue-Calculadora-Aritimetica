<script setup>
import Cabecalho from './components/Cabecalho.vue'
import Calculadora from './components/Calculadora.vue'
import Resultado from './components/Resultado.vue'
import { reactive } from 'vue'

const estado = reactive({
  acao: 'soma',
  valor1: '0',
  valor2: '0',
  resultado: '0'
})

const mudaValor = (e) => {
  if (e.target.id == 'input-1') {
    estado.valor1 = e.target.value
  } else if(e.target.id == 'input-2') {
    estado.valor2 = e.target.value
  } else {
    estado.acao = e.target.value
  }
}

const realizaCalculo = (e) => {
  mudaValor(e)

  if (estado.acao == 'soma') {
    estado.resultado = parseInt(estado.valor1) + parseInt(estado.valor2)
  } else if (estado.acao == 'subtracao') {
    estado.resultado = parseInt(estado.valor1) - parseInt(estado.valor2)
  } else if (estado.acao == 'multiplicacao') {
    estado.resultado = parseInt(estado.valor1) * parseInt(estado.valor2)
  } else if (estado.acao == 'divisao') {
    estado.resultado = parseInt(estado.valor1) / parseInt(estado.valor2)
  }
}
</script>

<template>
  <div class="container">
    <Cabecalho/>
    <Calculadora
      :realiza-calculo="evento => realizaCalculo(evento)"
    />
    <Resultado :carrega-resultado="estado.resultado"/>
  </div>
</template>

<style scoped>

</style>
