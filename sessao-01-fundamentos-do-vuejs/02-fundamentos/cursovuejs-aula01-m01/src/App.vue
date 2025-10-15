<script setup>
const modulo = 'Módulo 2'
const nomeDoAluno = '<span style="color: red;">Leandro</span>'
const btnDisabled = true
const atributos =  {
  style: 'color: red',
  id: 'titulo-principal',
  class: 'titulo-color'
}
const quantidade = 100

function verificaQuantidade(valor) {
  return valor > 10
}
</script>

<template>
  <div>
    <h1>Curso Vue.js Expert - {{ modulo }}</h1>

    <!-- Não renderiza o código html da variável -->
    <p>{{ nomeDoAluno }}</p>

    <!-- Renderiza o código html da variável -->
    <p v-html="nomeDoAluno"></p>

    <!-- Exibe o texto da variável modulo como title da tag html -->
    <h1 v-bind:title="modulo">Curso Vue.js Expert - {{ modulo }}</h1>

    <!-- Exibe o texto da variável modulo como title da tag html (forma reduzida) -->
    <h1 :title="modulo">Curso Vue.js Expert - {{ modulo }}</h1>

    <!-- Habilita/Desabilita o botão de acordo com a variável btnDisabled (Booleana) -->
    <button :disabled="btnDisabled">Um botão</button>

    <!-- Colocando atributos no elemento usando a variável -->
     <!-- <h1 id="titulo-principal" class="titulo-color" style="color: red;">Curso Vue.js Expert - Módulo 2</h1> -->
    <h1 v-bind="atributos">Curso Vue.js Expert - {{ modulo }}</h1>

    <!-- Utilizando expressões javascript -->
    <p>{{ 1 + 1 }}</p>
    <p>{{ quantidade + 5 }}</p>
    <p>{{ `A minha quantidade é ${quantidade}` }}</p>
    <p>{{ quantidade > 10 ? 'É maior que 10' : 'Não é maior que 10' }}</p>


    <!-- Utilizando uma função -->
    <p>{{ verificaQuantidade(quantidade) ? 'É maior que 10' : 'Não é maior que 10' }}</p>
  </div>
</template>
