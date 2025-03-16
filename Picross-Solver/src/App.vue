<script setup>
  import SizeInput from './components/SizeInput.vue'
  import PuzzleGrid from './components/PuzzleGrid.vue'
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
    <!-- grid size input, 2 numbers for x and y -->
    <form>
      <div>
        <SizeInput axis="x"/>
      </div>
      <div>
        <SizeInput axis="y"/>
      </div>
    </form>

    <!-- actual puzzle -->
    <form>
      <!-- generated grid + input on top & left -->
      <PuzzleGrid />

      <!-- solve button -->

      <!-- clear grid button -->

    </form>
  </main>
</template>

<style scoped>
</style>
