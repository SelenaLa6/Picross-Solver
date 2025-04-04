<script setup>
    // coordinate of square on grid
    const props = defineProps(['col', 'row'])
    const id = props.col + "-" + props.row
    // 0 = unknown, 1 = filled, 2 = flagged
    // let state = ref(0);
</script>

<template>
    <td :id="id" class="border border-gray-400 p-2"></td>
</template>