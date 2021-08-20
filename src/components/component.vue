<template>
  <div class="componente">
    <ul class="list">
      <li v-for="(Tarea, index) of Tareas" :key="index">
        {{ index }}. {{ Tarea }}
        <button @click="eliminardeLista(index)">Eliminar :c</button>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "componente",
  props: {
    Tareas: {
      type: Array,
    },
  },
  methods: {
    eliminardeLista(index) {
      this.$emit("eliminardeLista", index);
    },
  },
};
</script>

<style scoped>
.list {
  text-align: center;
  list-style: none;
}
button {
  margin: 10px;
  width: 100px;
  height: 30px;
  background-color: palevioletred;
  border-color: palevioletred;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  font-weight: 700;
  border-radius: 10%;
}

li {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  font-size: 30px;
  color: whitesmoke;
  font-weight: 600;
  margin-left: 40px;
}
</style>
