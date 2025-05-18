<template>
	<div id="app">
		<header>
			<h1>Витрина интернет магазина</h1>
		</header>
		<main>
			<ProductsList />
		</main>
	</div>
</template>

<script setup>
import ProductsList from './components/ProductsList.vue'
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
	color: white;
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