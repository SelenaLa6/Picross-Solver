<script setup>
    import RowInput from './RowNumInput.vue'
    import Square from './GridSquare.vue'

    const props = defineProps(['row', 'cols']);
</script>

<template>
    <td class="border border-gray-400 p-2">
        <RowInput :row="row"/>
    </td>
    <Square v-for="col in cols"></Square>
</template>