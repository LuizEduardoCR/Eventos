<script setup>
import { ref } from 'vue'
import ProdutsList from './components/ProdutsList.vue';
const produtos = ref([
  { id: 1, nome: 'Produto 1', preco: 19.99 },
  { id: 2, nome: 'Produto 2', preco: 29.99 },
  { id: 3, nome: 'Produto 3', preco: 39.99 },
  { id: 4, nome: 'Produto 4', preco: 49.99 },
]);
function excluirProduto(id) {
  const index = produtos.value.findIndex((produto) => produto.id === id);
  produtos.value.splice(index, 1);
}
function apagarTudo() {
  produtos.value=[]
}
</script>

<template>
  <h1>Meus Produtos</h1>
  <produts-list :produtos="produtos" @excluir="excluirProduto" @apagarTudo="apagarTudo" />

</template>

<style scoped></style>
