<script setup>
import {inject} from 'vue'

const props = defineProps(['product'])
const cart = inject('cart');

const addToCart = () =>{
    cart.push(props.product);
    alert(`${props.product.name} afegit al carret!`)
}
</script>

<template>
    <div class="product-item">
        <div class="product-info">
            <span class="name">
                {{ product.name }}
            </span>
            <span class="price">
                {{ product.price }}$
            </span>
        </div>
        <button @click="addToCart">Add to Cart</button>
    </div>
</template>

<style scoped>
</style>