<template>
<div class="p-3 bg-success">
    <h1>hola soy el Hijo {{numero}}</h1>
    <h4>Nombre :{{nombre}}</h4>
</div>
  
</template>
<script>
export default {
  name: "chijo",
  props:['numero'],
  data(){
      return {
          nombre: 'Javier jesus'

      }
  },
  mounted(){
      // evento emit para enviar valores al padre
      // el primer valor es el nombre de la variable a enviar y el segundo valor es el dato
      this.$emit('nombreHijo',this.nombre);
  }
 
};
</script>

<style scoped>
</style>