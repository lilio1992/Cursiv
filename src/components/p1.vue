<template>
  <div class="hello">
    <h2>{{msg}}</h2>
    <ul>
      <li v-for="fruta in frutas " :value="fruta.value" :key="fruta.value">
        {{fruta.nombre}}
        <input type="number" v-model.number="fruta.cantidad" />
        <span v-if="fruta.cantidad == 0">sin stock</span>
      </li>
    </ul>
    <h4>Total: {{sumarFrutas}}</h4>
  </div>
</template>

<script>
export default {
  name: "p1",
  props: {
    msg: String
  },
  data() {
    return {
      frutas: [
        { nombre: "pera", cantidad: 10 },
        { nombre: "Manzana", cantidad: 0 },
        { nombre: "Uva", cantidad: 8 }
      ]
      
    };
  },
  computed: {
    sumarFrutas() {
      var total =0;
     this.frutas .forEach(element =>
       total = total + element.cantidad);
    
      return total;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
