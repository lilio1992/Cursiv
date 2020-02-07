<template>
  <div class="hello">
  <h2>Color con clases</h2>
  <div
  :class="['p-3','text-white',fondo]"
  >
      <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Itaque, ipsam fuga? Earum, fugit? Repudiandae amet incidunt nobis, saepe perferendis animi totam aperiam sapiente hic facere rem autem harum veniam architecto?

      </p>
      <input type="text" v-model="fondo" class="form-control my-3">
  </div>
  <div class="text-white p-3"  :class="{'bg-info': color,'bg-success' :!color}">
       <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Itaque, ipsam fuga? Earum, fugit? Repudiandae amet incidunt nobis, saepe perferendis animi totam aperiam sapiente hic facere rem autem harum veniam architecto?

      </p>
  </div>
  <button @click="color =!color" class="btn btn-secondary">cambio color</button>
  </div>
</template>

<script>
export default {
  name: 'color',
  props: {

  },
  data() {
    return {
      fondo:'bg-warning',
      color: false
    }
  }
}
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
