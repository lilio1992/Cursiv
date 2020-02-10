<template>
  <div class="computado">
      <div>
          <h1>{{mensaje}}</h1>
          <h1>{{invertido}}</h1>
          <input type="text" class="form-control" v-model="mensaje" >
          <button class="btn btn-primary" @click="contador++">+</button>
          <button class="btn btn-dark" @click="contador--">-</button>
          <h1>{{contador}}</h1>
          <div class="progress">
            <div class="progress-bar"  :class="color" role="progressbar" :style="{'width': contador+'%'}" aria-valuenow="1" aria-valuemin="0" aria-valuemax="100">{{contador}}%</div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
  data() { return{
      mensaje : 'hola computado Invirtiendo valores',
      contador: 0
  }
      
  },
  computed: {
      invertido(){
          return this.mensaje.split('').reverse().join('');
      },
      color(){
          color
          return{
              'bg-success' :this.contador <=10,
              'bg-secondary' :this.contador > 10 && this.contador <= 20,
              'bg-warning' :this.contador > 20 && this.contador <= 50,
              'bg-danger' :this.contador > 50,

          }
      }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
