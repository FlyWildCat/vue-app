<template>
    <div class="products-list">
        <h1>Список товаров</h1>
        <ul>
            <li v-for="product in products" :key="product.id">
                <ProductCard :product="product" />
            </li>
        </ul>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import ProductCard from './ProductCard.vue';
// Импортируем данные из локального json-файла
import productsData from './products.json';

const products = ref(productsData);
</script>

<style scoped>
.products-list ul {
    list-style: none;
    padding-left: 0;
}

.products-list li {
    margin-bottom: 1rem;
}
</style>