<script setup>
  import TaskComponent from '@/components/TaskComponent.vue'
  import { ref } from 'vue';

  let newTask;

  const taskList = ref([
    'Levantarse',
    'Cepillarse',
    'Alimentarse'
  ])

  function deleteTask(index) {
    // console.log('KILL', index);
    taskList.value.splice(index, 1);
  }

  function addTask() {
    taskList.value.unshift(newTask);
    newTask = undefined;
  }

</script>

<template>
  <div class=" px-4 py-3 mx-auto mt-12 space-y-2 overflow-hidden rounded shadow-md bg-gray-50 w-96">
    <h1 class=" text-2xl font-semibold">
      Lista de Tareas
    </h1>

    <div class="flex">

      <input type="text" class="w-4/5 h-8 px-2 py-1 border border-r-0 border-green-500 rounded rounded-r-none outline-none" v-model="newTask">

      <span class=" w-1/5 h-8 py-1 text-white border bg-green-500 text-xl font-bold text-center rounded rounded-l-none leading-none hover:bg-green-700 hover:cursor-pointer" @click ="addTask">
        +
      </span>

    </div>

    <TaskComponent v-for="(task, index) in taskList" :key="index" :name="task" :index="index" @deleteTask="deleteTask"/>

  </div>
</template>

<style scoped>

</style>
