<script setup>
import { ref } from 'vue'


const novoItem = ref('')

const listaProdutos = ref([
  {
    id: 1,
    name: 'Peita',
    preco: 89.99,
    quantidade: 0
  },
  {
    id: 2,
    name: 'Calça',
    preco: 220.00,
    quantidade: 0
  },
  {
    id: 3,
    name: 'Tênis',
    preco: 369.99,
    quantidade: 0
  },
  {
    id: 4,
    name: 'Bag',
    preco: 49.99,
    quantidade: 0
  },
  {
    id: 5,
    name: 'Correntinha',
    preco: 40.00,
    quantidade: 0
  },
  {
    id: 6,
    name: 'Relógio',
    preco: 300.00,
    quantidade: 0
  },
])

function adicionar(itens) {
    itens.value.push(novoItem.value)
    novoItem.value = ''
  }
  function remover (index) {
    novoItem.value.splice(index, 1)
  }

</script>

<template>
  
  
  <ul>
    <li v-for="(itens, index) in listaProdutos" :key="novoItem.id"> {{ item }} 
      <div>{{ novoItem.name }}</div>
      <div>{{ novoItem.preco.toLocalestring('pt-br', { style: 'currency', currency: 'BRL'}) }}</div>
      <div>
        <button @click="adicionar">Adicionar</button> 
      </div>
      <button @click="remover(index)">Remover</button>
       
    </li>
  </ul>

</template>

<style scoped>
</style>
