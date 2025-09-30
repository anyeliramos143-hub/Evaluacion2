<template>
  <div>
    <h2>Formulario de Registro</h2>
    <form>
      <div>
        <label for="nombre">Nombre:</label>
        <input type="text" id="nombre" v-model="formulario.nombre" />
      </div>

      <div>
        <label for="direccion">Dirección:</label>
        <input type="text" id="direccion" v-model="formulario.direccion" />
      </div>

      <div>
        <label for="edad">Edad:</label>
        <input type="number" id="edad" v-model="formulario.edad" />
      </div>

      <button type="button" @click="enviarFormulario">Enviar</button>
    </form>

    <div v-if="enviado">
      <h3>Datos enviados:</h3>
      <p><strong>Nombre:</strong> {{ formulario.nombre }}</p>
      <p><strong>Dirección:</strong> {{ formulario.direccion }}</p>
      <p><strong>Edad:</strong> {{ formulario.edad }}</p>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      formulario: {
        nombre: '',
        direccion: '',
        edad: null
      },
      enviado: false
    };
  },
  methods: {
    enviarFormulario() {
      this.enviado = true;
    }
  }
};
</script>

<style scoped>
form div {
  margin-bottom: 10px;
}
label {
  display: inline-block;
  width: 100px;
}
input {
  padding: 5px;
}
button {
  padding: 8px 12px;
}
</style>
