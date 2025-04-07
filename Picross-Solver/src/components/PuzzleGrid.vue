<script setup>
    import { useTemplateRef, onMounted } from 'vue'
    import GridRow from './GridRow.vue'
    import ColInput from './ColNumInput.vue'
    const cols = defineModel('cols')
    const rows = defineModel('rows')

    let colClues = []
    let rowClues = []

    const puzzleGrid = useTemplateRef("puzzle")

    function collectClues() {
        // resets both clue arrays
        colClues.splice(0)
        rowClues.splice(0)
        
        const puzzleRows = puzzleGrid.value.children;

        //collect col clues (only first row)
        const firstRowCells = puzzleRows.item(0).children
        for (let i = 1; i < firstRowCells.length; i++) {
            const cellInputs = firstRowCells.item(i).querySelectorAll("input");
            let values = []
            cellInputs.forEach((input) => {
                values.push(input.value)
            })
            colClues.push(values)
        }

        //collect row clues (every other row)
        for (let i = 1; i < puzzleRows.length; i++) {
            const cellInputs = puzzleRows.item(i).querySelectorAll("input")
            let values = []
            cellInputs.forEach((input) => {
                values.push(input.value)
            })
            rowClues.push(values)
        }

        const test = document.getElementById("clues-test")
        test.textContent = colClues + " || " + rowClues
    }

    const buttonRef = useTemplateRef("button")

    onMounted(() => {
        buttonRef.value.addEventListener("click", collectClues)
    })

</script>

<template>
    <p>{{ cols }} by {{ rows }}</p>
    <table class="table-auto border-collapse border border-gray-400">
        <tbody ref="puzzle">
            <!-- top input row -->
            <tr>
                <td id="blank-square" class="border border-gray-400 p-2"></td>
                <td class="border border-gray-400 p-2" v-for="col in cols">
                    <ColInput :col="col"/>
                </td>
            </tr>
            <tr v-for="row in rows">
                <GridRow :row="row" :cols="cols"/>
            </tr>
        </tbody>
    </table>
    <button ref="button" type="button">Test Solve</button>
    <p id="clues-test">TEST</p>
</template>