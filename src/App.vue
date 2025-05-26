<template>
	<div id="app">
		<HeaderSearch @search="updateSearchResults"></HeaderSearch>
		<main>
			<section>
				<ProductsList :poisk="searchTerm"></ProductsList>
			</section>

			<!-- <section>
				<h2>Оформление заказа</h2>
				<OrderForm></OrderForm>
			</section>

			<section>
				<h2>Создание нового товара</h2>
				<NewProductForm></NewProductForm>
			</section> -->
		</main>
	</div>
</template>

<script setup>
import HeaderSearch from './components/HeaderSearch.vue';
import ProductsList from './components/ProductsList.vue';

import { ref } from 'vue';

const searchTerm = ref(''); // Текущий поисковый запрос

// Получаем данные от дочернего компонента HeaderSearch
const updateSearchResults = (term) => {
	searchTerm.value = term
}
</script>

<style>
* {
	box-sizing: border-box;
	margin: 0;
	padding: 0;
}

body {
	font-family: Arial, Helvetica, sans-serif;
	background-color: #fafafa;
	color: #333;
	text-align: center;
}

header {
	background-color: #4caf50;
	/* color: white; */
	padding: 1rem;
	text-align: center;
}

main {
	max-width: 1200px;
	margin: 0 auto;
	padding: 1rem;
	justify-self: center;
	align-content: center;
}
</style>