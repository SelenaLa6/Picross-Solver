<script setup>
    import GridRow from './GridRow.vue'
    import ColInput from './ColNumInput.vue'
    const cols = defineModel('cols')
    const rows = defineModel('rows')
</script>

<template>
    <p>Puzzle grid here</p>
    <p>{{cols }} by {{ rows }}</p>
    <table class="table-auto border-collapse border border-gray-400">
        <tbody>
            <!-- top input row -->
            <tr>
                <td class="border border-gray-400 p-2"></td>
                <ColInput v-for="col in cols"></ColInput>
            </tr>
            <GridRow v-for="row in rows" v-model:cols="cols"></GridRow>
        </tbody>
    </table>
</template>