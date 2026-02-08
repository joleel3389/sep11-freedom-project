<script setup>
  import {ref} from 'vue'
  const title = ref("Programming Quotes")
</script>

<template>
  <header>
      <h1>{{title}}</h1>
  </header>
</template>

<style scoped>
  header {
      color:#CCD6D9;
      margin-bottom:25px;
  }
</style>
