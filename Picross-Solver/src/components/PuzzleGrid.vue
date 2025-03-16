<script setup>
    import { ref, watchEffect } from 'vue'
    import SizeInput from './SizeInput.vue'

    const x = defineModel('x')
    const y = defineModel('y')
</script>

<template>
    <p>Puzzle grid here</p>
    <p>{{ x }} by {{ y }}</p>
</template>