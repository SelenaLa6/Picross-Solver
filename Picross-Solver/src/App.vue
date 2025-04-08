<script setup>
  import { ref, watch, onMounted, useTemplateRef } from 'vue'
  import SizeInput from './components/SizeInput.vue'
  import PuzzleGrid from './components/PuzzleGrid.vue'
  const rows = ref(5)
  const cols = ref(5)
  let matrix = []

  const solveButton = useTemplateRef("solve-btn")
  const puzzleGridEl = useTemplateRef("puzzlegrid")

  onMounted(() => {
    solveButton.value.addEventListener("click", () => {
      puzzleGridEl.value.solve()
    })
  })
  
  // update matrix whenever x or y changes
  // also resets matrix to all 0s if values have been changed
  watch([cols, rows], ([cols, rows]) => {

    if (cols > 0 && rows > 0) {
      matrix.splice(0)
      for (let i = 0; i < rows; i++) {
        matrix.push(new Array(cols).fill(0))
      }
    }

    // if (cols > 0 && rows > 0) {
    //   while (matrix.length < rows) {
    //     matrix.push(new Array(cols).fill(0));
    //   }
    //   while (matrix.length > rows) {
    //     matrix.pop();
    //   }

    //   for (let i = 0; i < matrix.length; i++) {
    //     if (matrix[i].length === cols) { break; }
    //     while (matrix[i].length < cols) {
    //       matrix[i].push(0);
    //     }
    //     while (matrix[i].length > cols) {
    //       matrix[i].pop();
    //     }
    //   }
    // }
  }, { immediate: true })


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
    <SizeInput axis="columns" v-model:size="cols"/>
    <SizeInput axis="rows" v-model:size="rows"/>
    <p>x: {{ cols }}</p>
    <p>y: {{ rows }}</p>
    
<!-- actual puzzle -->
    
    <!-- generated grid + input on top & left -->
    <PuzzleGrid ref="puzzlegrid" v-model:cols="cols" v-model:rows="rows"/>
    <p>{{ matrix }}</p>

    <!-- solve button -->
    <!-- click -> get 2 arrays of arrays from PuzzleGrid-->
    <button ref="solve-btn" type="button">Solve</button>
    

    <!-- clear grid button -->
    
    
  </main>
</template>

<style scoped>
</style>
