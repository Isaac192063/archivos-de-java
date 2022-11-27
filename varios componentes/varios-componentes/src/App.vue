<template>
  <div id="app">
    <ul>
      <li v-for="(nombre, i) in nombres" :key="i">{{ nombre }}</li>
    </ul>
    <input type="text" placeholder="nombres" v-model="nombre" />
    <button @click="agregarNombre">agregar</button>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data: function () {
    return {
      nombres: [],
      nombre: "",
    };
  },
  methods: {
    agregarNombre() {
      const nombre = this.nombre.trim();
      if (nombre == "") {
        return;
      }
      this.nombres.push(nombre);
      this.nombre = "";
    },
  },
};
</script>

<style lang="scss"></style>
