<template>
  <div class="home container-sm">
    <img alt="Vue logo" src="../assets/logo.png">
    <form class="align-middle container-sm mt-5">
      <label for="nombre" class="form-label">Ingrese su nombre, JavaScript lo leerá como un tipo de dato no primitivo</label>
      <input type="text" name="nombre" id="nombre" class="form-control" v-model.trim="nombre" style="max-width:400px;text-align:center;margin:0 auto;">
    </form>
    <Calculadora :nombre="nombre" v-if="enableSubmit"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Calculadora from './Calculadora.vue'

export default {
  name: 'Home',
  components: {
    Calculadora
  },
  data() {
    return {
      nombre: new String('')
    }
  },
  computed: {
    enableSubmit() {
      return this.nombre.length > 0 ? true : false;
    }
  }
}
</script>
