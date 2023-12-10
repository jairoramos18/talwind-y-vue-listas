<script setup>
const props = defineProps(
    {
        Tarea:{
            type: String,
            default: 'Tarea por defecto'
        },
        index: {
            type: Number
        }
    }
)

const emit = defineEmits(['borrarHijo'])

function borrar (index){
    emit('borrarHijo', index)
    //console.log('borrar hijo', index)
}

</script>

<template>
    <div class="flex justify-between px-4 py-1 mt-1 rounded bg-gray-200">
      {{ props.Tarea }}
      <span 
      @click="borrar(props.index)"
      class="transition-colors duration-300 hover:bg-red-700 hover:cursor-pointer px-2 text-center text-white bg-red-600 rounded">X</span>
    </div>
</template>