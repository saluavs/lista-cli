<template>
  <div>
    <ul>
      <li v-for="(tarea, index) in tareas" :key="tarea">
        {{tarea}}
        <button v-on:click="borrar(index)">Eliminar</button>
      </li>
    </ul>
  </div>
</template>

<script>
    export default {
        name: 'Items',
        props: { 
          msg: String,
          tareas:Array,
        },
        methods: {
            borrar(index){
            this.$emit('eliminarTarea', index)
        }
    },
}    
</script>

