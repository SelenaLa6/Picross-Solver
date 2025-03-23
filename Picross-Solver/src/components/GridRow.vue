<script setup>
    import RowInput from './RowNumInput.vue'
    import Square from './GridSquare.vue'

    const cols = defineModel('cols')
</script>

<template>
    <tr>
        <RowInput />
        <Square v-for="col in cols"></Square>
    </tr>
</template>