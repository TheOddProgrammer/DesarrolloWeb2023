<script setup>

    const props = defineProps({
        name: {
            type: String,
            default: "Unnamed"
        },
        index: {
            type: Number,
        }
    });

    const emit = defineEmits([
        'deleteTask',
        'addTask'
    ])

    function deleteTask(index) {
        console.log("Borrado", index);
        emit('deleteTask',index);
    }

</script>

<template>
    
    <div class="flex items-center justify-between px-4 py-2 bg-gray-200 rounded " id="data">

        <h1 class=" break-before-all text-justify pr-3">{{ props.name }}</h1>

        <span class=" h-6 inline-block px-2 text-white bg-red-800 rouded hover:bg-red-400 hover:cursor-pointer" @click="deleteTask(props.index)">
            X
        </span>
    </div>

</template>