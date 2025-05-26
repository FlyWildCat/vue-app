<template>
    <div class="products-list">
        <h1 v-if="props.poisk !== ''">Список товаров содержащих "{{ props.poisk }}"</h1>
        <h1 v-else>Список всех товаров</h1>
        <ul>
            <li v-for="product in filteredProducts" :key="product.id">
                <ProductCard :product="product" />
            </li>
        </ul>
    </div>
</template>

<script setup>
import { ref, onMounted, computed } from 'vue';
import ProductCard from './ProductCard.vue';

const props = defineProps({ poisk: String });

let allProducts = ref([])
// Загрузка данных при инициализации
onMounted(async() => {
	const response = await fetch('https://fakestoreapi.com/products');
	if (!response.ok) throw new Error("Ошибка загрузки");
	allProducts.value = await response.json();
})

const filteredProducts = computed(() => {
    if (!props.poisk || props.poisk === '') {return allProducts.value}
    return allProducts.value.filter(p => {
        const tl = p.title.toLowerCase();
        const cl = p.category.toLowerCase();
        const pl = props.poisk.toLowerCase();
        return tl.includes(pl) || cl.includes(pl)
    })
})
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