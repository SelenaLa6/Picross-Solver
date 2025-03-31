<script setup>
    import { onMounted } from 'vue'
    const props = defineProps(['col'])
    const id = "cIn-" + props.col;

    // onMounted(() => {
    //     const firstIn = document.getElementById(props.col);
    //     firstIn.addEventListener("keydown", (event) => {
    //         let key = event.key;
    //         if (key == "Enter") {
    //             let inputHTML = `<input required 
    //     type="number" 
    //     value="0" 
    //     min="0" 
    //     size="3"/>`
    //             event.currentTarget.insertAdjacentHTML("afterend", inputHTML);
    //         }
    //     });
    // })

    onMounted(() => {
        const container = document.getElementById(id);
        container.firstElementChild.addEventListener("keydown", addDelete)
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


</script>

<template>
        <div class="flex flex-col" :id="id">
            <input required
            type="number" 
            value="0"
            min="0" 
            size="3"/>
        </div>
</template>

<style scoped>
</style>