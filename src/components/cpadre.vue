<template>
  <div class="p-5 bg-dark text-white">
    <h1>hola soy el padre numero padre:{{numeroPadre}}</h1>
    <button class="btn btn-primary" @click="numeroPadre++">+</button>
    <h4>{{nombrePadre}}</h4>
    <!-- :numero = es la varable enbevida que recibe y asigna el valor del elemento padre hacia el hijo -->
   <!-- @nombreHijo = variabla que envia el valor al padre, asignando el metodo event para que reasigne el valor a la variabloe del padre -->
   <chijo :numero="numeroPadre" @nombreHijo="nombrePadre= $event" />
  </div>
</template>
<script>
import chijo from "./chijo.vue";
export default {
  components: {
    chijo
  },
  data(){
      return{
          numeroPadre :0,
          nombrePadre: ''
      }
  }
}
</script>