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
                <td class="border border-gray-400 p-2" v-for="col in cols">
                    <ColInput :col="col"/>
                </td>
            </tr>
            <tr v-for="row in rows">
                <GridRow :row="row" :cols="cols"/>
            </tr>
        </tbody>
    </table>
</template>