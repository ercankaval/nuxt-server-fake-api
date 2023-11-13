<script setup lang="ts">

const { data: products, pending } = await useAsyncData("products", () =>
    $fetch("/api/products")
);

const refresh = () => refreshNuxtData("products");

</script>

<template>
  <div>
    <p>{{ pending ? "Loading..." : products }}</p>
    <button @click="refresh">Refresh</button>
  </div>
</template>
