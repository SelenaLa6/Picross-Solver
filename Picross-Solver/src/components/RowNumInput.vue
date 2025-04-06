<script setup>
    import { onMounted } from 'vue'
    const props = defineProps(['row']);
    const id = "rIn-" + props.row;

    onMounted(() => {
        const container = document.getElementById(id);
        container.firstElementChild.addEventListener("keydown", addDelete);
        container.firstElementChild.addEventListener("blur", defaultToZero);
    })

    function addDelete(event) {
        let key = event.key;
        let current = event.currentTarget;
        if (key === "Enter") {
            const inputHTML = `<input required 
        type="number" 
        value="0" 
        min="0" 
        size="3"/>`;
            current.insertAdjacentHTML("afterend", inputHTML);
            current.nextElementSibling.addEventListener("keydown", addDelete);
            current.nextElementSibling.addEventListener("blur", defaultToZero);
            current.nextElementSibling.focus();
        } else if (key === "Backspace"
        && current.value === ""
        && current.parentElement.childElementCount > 1) {
            event.preventDefault();
            if (current.previousElementSibling) {
                current.previousElementSibling.focus();
            } else {
                current.nextElementSibling.focus();
            }
            current.remove();
        }
        //puts focus to end of input
        var val = document.activeElement.value;
        document.activeElement.value = "";
        document.activeElement.value = val;
    }

    function defaultToZero(event) {
        if (event.currentTarget.value === "")
            event.currentTarget.value = "0";
    }

</script>

<template>
    <div class="flex flex-row" :id="id">
        <input required
            type="number" 
            value="0"
            min="0" 
            size="3"/>
    </div>
</template>

<style scoped>
</style>