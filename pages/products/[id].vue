<template>
  <div>
    <p>product details for {{ id }}</p>
    <p>lorem ipsum</p>
  </div>
</template>

<script setup>
  const { id } = useRoute().params
</script>

<style scoped>
</style>