<script setup>
import { inject } from 'vue';
import ProductItem from './ProductItem.vue';

const products = inject('products');
</script>
<template>
    <div class="category-list">
        <h2>Productes</h2>
        <div>
            <ProductItem v-for="p in products" :key="p.name" :product="p" />
        </div>
    </div>
</template>
