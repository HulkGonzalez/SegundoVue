<template>
  <div id="app">
    <div class="container">
      <h1>Crear una nueva tarea</h1>
    <form v-on:submit.prevent="crearTarea">
      <p>Tarea: <input type="text" v-model="nombre" /></p>
      <button type="submit">Crear</button>
    </form>

    <h2>Lista</h2>

    <ul class="" v-for="(tarea, index) in tareas" :key="tarea">
      <li class="">{{ index }} - {{ tarea.nombre }}</li>
    </ul>
    </div>
  </div>
</template>

<script>
export default {
  el: "App",
 
  data() {
    return {
      nombre: "",
      tareas: [],
    };
  },
  methods: {
    crearTarea: function () {
      this.tareas.push({
        nombre: this.nombre,
      });
    },
  },
};
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
