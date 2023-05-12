<script setup>
import { ref } from 'vue'

const enviar = ref(false)
let valorcarrinho = ref(0)
const carrinho = ref([])
const produtos = ref([
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

  function addCarrinho(id, name,preco,quantidade){
    if(quantidade == 0) {
      alert('Adicione o produto primeiro antes de colocar no carrinho')
    } else{carrinho.value.push({id, name,preco,quantidade})}
  }
  function limparCarrinho(){
    carrinho.value = []
    valorcarrinho.value = 0
}
function verCarrinho(){
  enviar.value = !enviar.value
}
</script>

<template>
  

  <ul>
    <div class="produtos">
    <li v-for="(item, index) in produtos" :key="index">
      <div>{{ item.name }}</div>
      <div>{{ item.preco.toLocaleString('pt-br', { style: 'currency', currency: 'BRL'}) }}</div>
      <div>Quantidade: {{ item.quantidade }}</div>
      <div>
        <button @click="item.quantidade++">Adicionar</button>
      <button @click="item.quantidade--" v-if="item.quantidade > 0">Remover</button>
      </div>
      <div>
        <button @click="addCarrinho(item.id, item.name, item.preco, item.quantidade)">adicionar ao carrinho</button>
      </div>
    </li>
  </div>
  </ul>
  <button @click="verCarrinho()">ver carrinho</button>
  <div class="Carrinho" v-if="enviar">
  <ul>
      <li v-for="(item,index) in carrinho" :key="index">
        <div>{{ item.name }}</div>
        <div>{{ item.preco.toLocaleString('pt-br', { style: 'currency', currency: 'BRL'}) }}</div>
        <div>Quantidade: {{ item.quantidade }}</div>
      </li>
      <button @click="limparCarrinho()">Limpar carrinho</button>
  </ul>
</div>

</template>

<style scoped>
  li{
    list-style: none;
    margin: 15px 20px;
  }
  .produtos{
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    width: 450px;  
  }
  button{
    margin: 4px 0;
  }
</style>
