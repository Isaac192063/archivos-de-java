<template>
  <div id="app">
    <!-- <label for="">digite lo que usted quera pa</label><br />
    <input type="text" v-model.trim="w" />
    <p>{{ w }}</p>
    <p>limpiar</p> -->
    <h1 v-for="(cosa, index) in platas" :key="index">
      {{ index + 1 }} - {{ cosa }}
    </h1>
    <input type="text" name="" id="a" v-model="nuevaTarea" />
    <button @click="imprimirUnNumero">oprima el boton</button>
    <div></div>
    <div v-show="grande">mensaje</div>
    <p v-if="grande">mucho loco</p>
    <p v-else>normal pa</p>
    <button @click="veces += 1">haga clic aqui papu</button>
    <p>se ha hecho clic {{ veces }}</p>

    <input type="text" placeholder="ingrese nombre" v-model="nombre" />
    <button @click="errroVacio">validar</button>
    <p v-if="errroVacio">Este campo esta vacio</p>
    <p v-else>no pasa nada papu</p>

    <h1 v-for="(cosa, i) in cosas" :key="i">
      <p v-if="i % 2 == 0" style="background-color: aquamarine">{{ cosa }}</p>
      <p v-else style="background-color: aqua">{{ cosa }}</p>
    </h1>
  </div>
</template>

<script>
export default {
  name: "App",
  data: function () {
    return {
      cosas: ["camilo", "andres", "pedro"],
      platas: ["gremio", "hjas", "seco"],
      nuevaTarea: "",
      veces: 1,
      nombre: "",
    };
  },
  methods: {
    imprimirUnNumero() {
      const msg = this.nuevaTarea.trim();

      if (msg.length == 0) {
        // alert("debe ingresar un valor");
        // document.getElementById("a").focus();
        this.nuevaTarea = "";
        return;
      }
      this.nuevaTarea = "";
      this.platas.push(msg);
    },
  },
  computed: {
    grande() {
      if (this.platas.length > 4) {
        return true;
      } else {
        return false;
      }
    },
    errroVacio() {
      if (this.nombre == "") {
        return true;
      }
      return false;
    },
  },
};
</script>

<style lang="scss">
// h1 > p {
//   display: inline-block;
// }
// p {
//   display: inline;
// }
h1 {
  display: inline-block;
}
h1 > P {
  padding: 15px;
}
h1 > p:hover {
  background-color: rgb(0, 0, 0);
}
</style>
