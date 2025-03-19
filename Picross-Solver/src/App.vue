<script setup>
  import { ref, watch } from 'vue'
  import SizeInput from './components/SizeInput.vue'
  import PuzzleGrid from './components/PuzzleGrid.vue'
  const rows = ref(5)
  const cols = ref(5)
  let matrix = []
  
  // update matrix whenever x or y changes
  watch([cols, rows], ([cols, rows]) => {

    if (cols > 0 && rows > 0) {
      while (matrix.length < rows) {
        matrix.push(new Array(cols).fill(0));
      }
      while (matrix.length > rows) {
        matrix.pop();
      }

      for (let i = 0; i < matrix.length; i++) {
        if (matrix[i].length === cols) { break; }
        while (matrix[i].length < cols) {
          matrix[i].push(0);
        }
        while (matrix[i].length > cols) {
          matrix[i].pop();
        }
      }


    }
  })

</script>

<template>
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
    <SizeInput axis="x" v-model:size="cols"/>
    <SizeInput axis="y" v-model:size="rows"/>
    <p>x: {{ cols }}</p>
    <p>y: {{ rows }}</p>
    
<!-- actual puzzle -->
    
    <!-- generated grid + input on top & left -->
    <PuzzleGrid v-model:x="cols" v-model:y="rows"/>
    <p>{{ matrix }}</p>

    <!-- solve button -->

    <!-- clear grid button -->

    
  </main>
</template>

<style scoped>
</style>
