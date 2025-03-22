<script setup>
    const props = defineProps(['axis'])
    const size = defineModel('size')
</script>

<template>
    <p>Enter number of {{ axis }}:</p>
    <input required
    v-model="size"
    type="number"
    value="5"
    min="1" />
</template>