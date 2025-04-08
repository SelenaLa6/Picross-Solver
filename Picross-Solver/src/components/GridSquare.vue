<script setup>
    // coordinate of square on grid
    import { ref, watch, useTemplateRef} from 'vue'
    const props = defineProps(['col', 'row'])
    const id = props.col + "-" + props.row
    // 0 = blank, 1 = filled, -1 = flagged
    let state = ref(0)
    const square = useTemplateRef("square")

    watch([state], ([state]) => {
        if (state == 0) {
            square.value.style.backgroundColor = ""
        } else if (state == 1) {
            square.value.style.backgroundColor = "gray"
        } else {
            square.value.style.backgroundColor = "yellow"
        }
    })
</script>

<template>
    <td :id="id" ref="square" class="border border-gray-400 p-2"></td>
</template>