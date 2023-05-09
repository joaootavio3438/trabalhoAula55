<script setup>
import { ref } from 'vue'


// const item = ref('')

const listaProdutos = ref([
  {
    id: 1,
    name: 'Camisa',
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
    name: 'Corrente de pescoço',
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

// function adicionar(novoItem) {
//     itens.value.push(novoItem.value)
//     novoItem.value = ''
//   }
//   function remover (index) {
//     novoItem.value.splice(index, 1)
//   }

</script>

<template>
  
  
  <ul>
    <li v-for="(item, index) in listaProdutos" :key="item.id"> {{ item }} 
      <div>{{ item.name }}</div>
      <div>{{ item.preco.toLocaleString('pt-br', { style: 'currency', currency: 'BRL'}) }}</div>
      <div>
        <button @click="adicionar">Adicionar</button> 
      </div>
      <button @click="remover(index)">Remover</button>
       
    </li>
  </ul>

</template>

<style scoped>
</style>
