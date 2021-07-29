<template>
  <div class="formulario">
    <img src="./assets/logo.png " alt="logo vue">
      <div>
          <label for="">Tarea </label>
          <input v-model="nuevaLista"  placeholder="ingresa nueva tarea" >
          <button @click="agregarTarea">Añade</button>
          <Items msg="Listas" :tareas="tareas" @eliminarTarea="delTarea"></Items>
      </div>
  </div>
</template>

<script>
import Items from './components/Items.vue'

export default {
  name: 'App',
  data(){
    return{
      tareas:[],
      nuevaLista:"",
    }
  },
  components: {
    Items
  },
  methods: {
    agregarTarea(){
        this.tareas.push(this.nuevaLista)
        this.nuevaLista = ""
    },
    delTarea(index){
      this.tareas.splice(index,1)
    }
  },
}
</script>


<style>
    .formulario {
        text-align: center;
    }
    input, button {
        padding: 5px;
    }
    ul {
        width: 30%;
        margin: 0 auto;
        text-align: left;
        padding-left: 16em;
    }
</style>