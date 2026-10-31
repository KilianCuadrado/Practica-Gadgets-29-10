<script setup>
defineProps({
    product: {
        type: Object,
        required: true
    }
});
</script>

<template>
    <li>{{ product.name }} - {{ product.price }}$</li>
</template>