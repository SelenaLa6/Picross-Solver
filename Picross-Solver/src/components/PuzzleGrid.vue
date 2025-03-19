<script setup>
    import GridSquare from './GridSquare.vue'
    const x = defineModel('x')
    const y = defineModel('y')
</script>

<template>
    <p>Puzzle grid here</p>
    <p>{{ x }} by {{ y }}</p>
    <div class="table">
        
    </div>
</template>