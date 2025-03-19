<script setup>
    const props = defineProps(['axis'])
    const size = defineModel('size')
</script>

<template>
    <p>Enter {{ axis }} dimension: </p>
    <input required
    v-model="size"
    id="{{ axis }}-axis"
    type="number"
    value="5"
    min="1" />
</template>