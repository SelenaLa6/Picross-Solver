<script setup>
    import { onMounted } from 'vue'
    const props = defineProps([])

    onMounted(() => {
        const clueArea = document.querySelector("textarea")
        clueArea.addEventListener("input", autoResize, false)
    })

    function autoResize() {
        this.style.height = "auto";
        this.style.height = this.scrollHeight + "px";
    }

</script>

<template>
    <td class="border border-gray-400 p-2">
        <textarea rows="2" cols="2" style="resize: none"></textarea>
    </td>
</template>

<style scoped>
</style>