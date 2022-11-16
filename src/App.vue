<script setup>
import Add from './components/Add.vue'
import Epreuves from './components/Epreuves.vue'
</script>

<template>
  <header>
    <h1>Bulletins de notes 📊</h1>
  </header>
  <main>
    <Add />
    <Epreuves />
  </main>
</template>

<style scoped>
header {
  color:white;
  text-align: center;
  margin:30px;
}
</style>
