<script setup>
    import GridSquare from './GridSquare.vue'
    import ColInput from './ColNumInput.vue'
    const cols = defineModel('cols')
    const rows = defineModel('rows')
</script>

<template>
    <p>Puzzle grid here</p>
    <p>{{cols }} by {{ rows }}</p>
    <table class="table-fixed border-collapse border border-gray-400">
        <tbody>
            <!-- top input row -->
            <tr>
                <ColInput />
            </tr>  
        </tbody>
    </table>
</template>