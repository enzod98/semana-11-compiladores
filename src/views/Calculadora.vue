<template>
  <div id="calc">
    <figure>
      <blockquote class="blockquote">
        <h2>
          ¡Hola <u>{{ nombre }}</u
          >!
        </h2>
      </blockquote>
      <figcaption class="blockquote-footer">
        Un nombre refachero de tipo 
        <cite title="Source Title">String</cite>
      </figcaption>
    </figure>

    <p>JavaScript tiene la posibilidad de acceder a varias funciones a partir de una variable tipo <cite title="Source Title">String</cite></p>
    <p>Estos pueden ser:</p>
    <ul style="text-align:left">
      <li><b>length</b>: Permite saber la cantidad de caracteres del String. El String.length de <b>{{nombre}}</b> es: <i>{{ nombre.length }}</i></li>
      <li><b>toUpperCase()</b>: Permite convertir a mayúsculas todo el String. El String.toUpperCase() de <b>{{nombre}}</b> es: <i>{{ nombre.toUpperCase() }}</i></li>
      <li><b>toLowerCase()</b>: Permite convertir a minúsculas todo el String. El String.toLowerCase() de <b>{{nombre}}</b> es: <i>{{ nombre.toLowerCase() }}</i></li>
      <li><b>split()</b>: Permite convertir en un array todo el String, en donde cada caracter es una posición del array. El String.split() de <b>{{nombre}}</b> es: <i>{{ nombre.split('') }}</i></li>
    </ul>
    <p><b>Conclusión</b>: los datos de tipo complejo nos dan la facilidad de realizar acciones rápidas sin hacer mucho código. Facilitando nuestra programación</p>
    <hr>
    <h1>Los tipos de dato primitivos</h1>
    <p>Los tipos primitivos no tienen métodos ni propiedades</p>
    <p>Son útiles para manejo de números o booleanos, por ejemplo, aquí está una mini calculadora con la cual se hacen operaciones matemáticas a partir de datos primitivos</p>
    <form class="align-middle container-sm mt-5 d-flex justify-content-center">
      <input type="number" name="num1" id="num1" class="form-control" v-model.trim="num1" style="max-width:100px;text-align:center;margin:0">
      <select class="form-select" aria-label="select example" style="max-width:100px;text-align:center" v-model="operacion">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="/">/</option>
        <option value="*">*</option>
      </select>
      <input type="number" name="num2" id="num2" class="form-control" v-model.trim="num2" style="max-width:100px;text-align:center;margin:0">
    </form>
      <p class="mt-4">Resultado: {{ result }}</p>
  </div>
</template>

<script>
export default {
  name: "Calculadora",
  props: {
    nombre: String
  },
  data() {
    return {
      num1: 0,
      num2: 0,
      operacion: '+'
    }
  },
  computed: {
    result() {
      switch (this.operacion){
        case '+':
          return parseInt(this.num1) + parseInt(this.num2);
        case '-':
          return parseInt(this.num1) - parseInt(this.num2);
        case '*':
          return parseInt(this.num1) * parseInt(this.num2);
        case '/':
          return parseInt(this.num1) / parseInt(this.num2);
      }
    }
  },
};
</script>

<style scoped>
#calc {
  max-width: 1000px;
  margin: 0 auto;
  padding: 1rem 0 4rem 0;
}
figure {
  text-align: left;
}
</style>
