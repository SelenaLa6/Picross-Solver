<script setup>
</script>

<template>
  <head>
    <title>Picross Solver</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link href="/src/styles.css" rel="stylesheet" />
  </head>
  <header>
    <h1>Picross Solver</h1>
    <p>Picross, AKA nonogram, is a puzzle involving numbers.</p>
  </header>
  <main>
    <!-- grid size input, 2 numbers for x and y -->
    <form></form>

    <!-- actual puzzle -->
    <form>
      <!-- generated grid + input on top & left -->
      <div></div>

      <!-- solve button -->

      <!-- clear grid button -->

    </form>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
