<template>
    <div class="product-card">
        <div>
            <img :src="product.image" :alt="product.title" />
        </div>
        <div>
            <div><span class="price"><strong>Цена: </strong> {{ product.price }} ₽</span></div>
            <div><span class="title"><strong>Название: </strong> {{ product.title }}</span></div>
            <div><span class="category"><strong>Категория: </strong> {{ product.category }}</span></div>
            <div><span class="rating rate"><strong class="rate-title">Рейтинг: </strong>{{ product.rating.rate }}</span>
                <span class="rating"> {{ product.rating.count }} отзывов</span>
            </div>
        </div>
    </div>
</template>

<script setup>
defineProps({
    product: Object
})
</script>

<style scoped>
.product-card {
    border: 1px solid #ddd;
    padding: 1rem;
    margin-bottom: 1rem;
}

.product-card img {
    max-width: 10%;
    height: auto;
}

.product-card .rating {
    margin-right: 4px;
}

.product-card .rate-title {
    color: gray;
}

.product-card .price,
.title,
.category {
    text-align: center;
}
</style>