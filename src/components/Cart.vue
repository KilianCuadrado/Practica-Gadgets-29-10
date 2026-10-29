<script>
import { inject,computed } from 'vue';
const cart =inject('cart');
const total = computed(()=>
    cart.reduce((sum,p)=>sum + p.price, 0)
);
</script>
<template>
    <div>
        <h2>Carret</h2>
        <ul>
            <li v-for="p in cart" :key="p.name">{{ p.name }} - {{ p.price }}</li>
        </ul>
    </div>
</template>