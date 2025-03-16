<script setup>
    import { ref } from 'vue'
    const props = defineProps(['axis'])
    const size = ref(5)
</script>

<template>
    <p>Enter {{ axis }} dimension: </p>
    <input required
    v-model="size"
    id="{{ axis }}-size"
    type="number"
    value="5"
    min="1" />
    <!-- <p> Test: {{ size }}</p> -->
</template>