<script setup>
    import { onMounted } from 'vue'

    onMounted(() => {
        const clueArea = document.querySelector("textarea")
        clueArea.addEventListener("input", autoResize, false)
    })

    function autoResize() {
        this.style.width = "auto";
        // this.style.width = this.scrollWidth + "px";
        this.style.width = this.value.length + "ch";
    }   

</script>

<template>
    <td class="border border-gray-400 p-2">
        <textarea rows="1" cols="2" style="resize: none; min-width: 10px"></textarea>
    </td>
</template>