<script setup>
    import GridSquare from './GridSquare.vue'
    import ColInput from './ColNumInput.vue'
    const x = defineModel('x')
    const y = defineModel('y')
</script>

<template>
    <p>Puzzle grid here</p>
    <p>{{ x }} by {{ y }}</p>
    <table class="table-fixed border-collapse border border-gray-400">
        <tbody>
            <!-- top input row -->
            <tr>
                <ColInput />
                <ColInput />
                <ColInput />
            </tr>  
        </tbody>
    </table>
</template>