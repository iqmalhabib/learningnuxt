<template>
  <div>
    <h2>About</h2>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ut, recusandae
      corporis dolorem ad, obcaecati repudiandae inventore esse iusto deserunt
      aliquid
    </p>
    <div>{{  data }}</div>
  </div>
</template>

<script setup>
  const { data } = await useFetch('/api/test?name=mario')
</script>

<style scoped>
</style>