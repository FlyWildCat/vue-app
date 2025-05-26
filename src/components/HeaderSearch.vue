<template>
  <header class="app-header">
    <h1>Магазин</h1>
    <form @submit.prevent="handleSearch">
      <span>Поиск по товарам содержащим: </span>
      <input type="search" placeholder="Название/Категория товара..." v-model="searchQuery"/>
      <button type="submit">Искать</button>
    </form>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const searchQuery = ref('')

const emit = defineEmits(['search']);

const handleSearch = () => {
  emit('search', searchQuery.value);
}
</script>

<style scoped>
.app-header {
  background-color: #fafafa;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>