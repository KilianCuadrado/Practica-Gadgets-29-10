<script setup>
import { computed, inject } from 'vue';
import CartItem from './CartItem.vue';

const cart = inject('cart');

const total = computed(() =>
    cart.reduce((sum, product) => sum + product.price, 0)
);

const itemCount = computed(() => cart.length);

const clearCart = () => {
    cart.splice(0, cart.length);
};
</script>
<template>
    <div class="cart">
        <h2>Carret</h2>
        <p>{{ itemCount }} article{{ itemCount === 1 ? '' : 's' }}</p>
        <ul>
            <CartItem
                v-for="(product, index) in cart"
                :key="`${product.name}-${index}`"
                :product="product"
            />
        </ul>
        <p>Total: {{ total }}$</p>
        <button type="button" @click="clearCart">🗑️ Buida carret</button>
    </div>
</template>