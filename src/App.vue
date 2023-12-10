<script setup>
import TaskComponent from '@/components/TaskComponent.vue';
import { ref } from 'vue';

const Tareas = ref(['Ninguna', 'Dormir', 'Descansar'])

function deleteTask(index) {
  Tareas.value.splice(index, 1)
}
</script>

<template>
  <div class="px-4 py-2 w-96 bg-gray-100 shadow-md rounded mx-auto mt-12">
    <h1 class="text-center text-2xl font-semibold ">
      Lista de Tareas
    </h1>
    <div class="flex mt-2">
      <input type="text" class="w-4/5 h-8 px-2 py-1 border border-green-600 rounded rounded-r-none outline-none">
      <span class="transition-colors duration-300 hover:bg-green-700 hover:cursor-pointer w-1/5 h-8 text-xl font-bold text-center text-white bg-green-600 rounded rounded-l-none">
        +
      </span>
    </div>
    <TaskComponent
    v-for="(Tarea, index) in Tareas"
    :key="index"
    :Tarea="Tarea"
    :index="index"
    @borrarHijo="deleteTask"
    />
    

  </div>
</template>
