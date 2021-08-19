<template>
  <div id="App">
    <h1>Lista de actividades</h1>
    <input
      type="text"
      required
      v-model="ActividadNueva"
      placeholder="Ingrese nueva actividad c:"
    />
    <button @click="AgregarALista">Agregar!</button>
    <componente
      :Tareas="Tareas"
      @EliminardeLista="EliminardeLista"
    ></componente>
  </div>
</template>

<script>
import componente from "./components/component.vue";

export default {
  name: "App",
  components: { componente },
  data: () => ({
    ActividadNueva: "",
    Tareas: [],
  }),
  methods: {
    AgregarALista: function () {
      this.Tareas.push(this.ActividadNueva);
      this.ActividadNueva = "";
    },
    EliminardeLista: function () {
      this.Tareas.splice(this.Tareas.indexOf(this.ActividadNueva), 1);
      this.ActividadNueva = "";
    },
  },
};
</script>

<style lang="scss" scoped>
html,
body {
  margin: 0;
}
#App {
  background-color: cadetblue;
  margin-left: 120px;
  margin-right: 120px;
  height: 570px;
  border-radius: 3%;
}

h1 {
  text-align: center;
  font-size: 50px;
  color: white;
  padding-top: 50px;
}

input {
  text-align: center;
  margin-left: 390px;
  width: 250px;
  height: 25px;
  font-size: 15px;
}

button {
  text-align: center;
  margin: 10px;
  width: 100px;
  height: 50px;
  background-color: paleturquoise;
  border-color: paleturquoise;
  border-radius: 10%;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  font-weight: 700;
}
</style>
