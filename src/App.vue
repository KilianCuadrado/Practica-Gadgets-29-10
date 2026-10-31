<script setup>
import { reactive, provide } from 'vue';
import CategoryList from './components/CategoryList.vue'
import Cart from './components/Cart.vue'

const cart = reactive([]);
const products = [
  { name: "Auriculars Wireless 🎧", price: 50 },
  { name: "Smartwatch ⌚", price: 120 },
  { name: "Teclat Mecànic ⌨️", price: 80 },
  { name: "Altaveu Bluetooth 🔊", price: 60 }
];

provide ('cart', cart);
provide('products', products);

</script>

<template>
  <div class="app-container">
    <h1>Botiga de gatgedts</h1>
    <div>
      <CategoryList />
      <Cart />
    </div>
  </div>
</template>

<style scoped>

.app-container {
  max-width: 900px;
  margin: 0 auto;
  padding: 2rem;
  font-family: Arial, sans-serif;
}

.app-container > div {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 2rem;
}

.category-list,
.cart {
  padding: 1rem;
  border: 1px solid #ddd;
  border-radius: 6px;
  background: #f8f8f8;
}

.product-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
  padding: 0.75rem 0;
  border-bottom: 1px solid #ddd;
}

.product-info {
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
}

.price {
  font-weight: bold;
}

button {
  padding: 0.5rem 0.75rem;
  border: 0;
  border-radius: 4px;
  background: #2563eb;
  color: white;
  cursor: pointer;
}

button:hover {
  background: #1d4ed8;
}



</style>
