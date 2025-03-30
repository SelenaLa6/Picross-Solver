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
        const firstIn = document.getElementById(props.col);
        firstIn.addEventListener("keydown", (event) => {
            let key = event.key;
            if (key == "Enter") {
                let inputHTML = `<input required 
        type="number" 
        value="0" 
        min="0" 
        size="3"/>`
                event.currentTarget.insertAdjacentHTML("afterend", inputHTML);
            }
        });
    })

    function addDelete(event) {
        let key = event.key;
        if (key == "Enter") {
            const inputHTML = `<input required 
        type="number" 
        value="0" 
        min="0" 
        size="3"`;
            event.currentTarget.insertAdjacentHTML("afterend", inputHTML);
        } else if ( key == "Backspace") {
            ;
        }
    }


</script>

<template>
        <div class="flex flex-col" :id="id">
            <!-- :id="col" -->
            <input required
            type="number" 
            value="0"
            min="0" 
            size="3"/>
        </div>
</template>

<style scoped>
</style>