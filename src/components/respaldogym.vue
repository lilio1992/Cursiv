<template>
  <div class="container mt-5">
    <h3>{{titulo}}</h3>
    <input type="text" class="form-control my-3" v-on:keyup.enter="tareasNew" v-model="nuevaTarea" />
    <button class="btn btn-primary" @click="tareasNew">Agregar</button>
    <div class="mt-3">
      <div
        :class ="[alert, item.estado ? 'alert-success':'alert-danger']"
        role="alert"
        v-for="(item, index) in tareas"
        :key="item.value"
      >
        <div class="d-flex justify-content-between alig-items-center">
          <div>
            <p>{{index}}- {{item.nombre}}-{{item.estado}}</p>
          </div>
          <div>
            <button class="btn btn-success btn-sm" @click="cambioTarea(index)">Ok</button>

            <button class="btn btn-danger btn-sm" @click="eliminar(index)">X</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "gym",
  props: {},
  data() {
    return {
      titulo: "Gym con vue",
      nuevaTarea: "",
      tareas: []
    };
  },
  methods: {
    tareasNew :function() {

      this.tareas.push ({
          nombre :this.nuevaTarea,
          estado: false
      });
     
      this.nuevaTarea = "";
      localStorage.setItem('gym-vue',JSON.stringify(this.tareas));
      return this.tareas;

    },
    cambioTarea : function(index){
        this.tareas[index].estado= true;
        localStorage.setItem('gym-vue',JSON.stringify(this.tareas));
        return this.tareas;
        

    },
    eliminar : function(index){
        this.tareas.splice(index,1);
        localStorage.setItem('gym-vue',JSON.stringify(this.tareas));
        return this.tareas;

    }
  },
  created: function(){
      let datodDB= JSON.parse(localStorage.getItem('gym-vue'));
      if(datodDB){
          this.tareas=[];
      }else{
          this.tareas= datodDB;
      }
    return true
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
