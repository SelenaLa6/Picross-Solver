<script setup>
  import { ref } from 'vue'
  import SizeInput from './components/SizeInput.vue'
  import PuzzleGrid from './components/PuzzleGrid.vue'
  const x = ref(5)
  const y = ref(5)
</script>

<template>
  <head>
    <title>Picross Solver</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link href="/src/styles.css" rel="stylesheet" />
  </head>
  <header>
    <div>
      <h1>Picross Solver</h1>
    </div>
    <div>
      <p>Picross, AKA nonogram, is a puzzle involving numbers.</p>
    </div>
  </header>
  <main>
<!-- size inputs -->
    <SizeInput axis="x" v-model:size="x"/>
    <SizeInput axis="y" v-model:size="y"/>
    
    <!-- actual puzzle -->
    <form>
      <!-- generated grid + input on top & left -->
      <PuzzleGrid v-model:x="x" v-model:y="y"/>

      <!-- solve button -->

      <!-- clear grid button -->

    </form>
  </main>
</template>

<style scoped>
</style>
