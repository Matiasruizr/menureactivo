<template>
  <div class="product">
    <a href="" class="imagen">
      <img v-bind:src="product.foto">
    </a>
    <div class="texto">
      <h2>{{ product.nombre }}</h2>
      <h3>{{ product.ingredientes }}</h3>
      <h4>Valor ${{ product.valor }}</h4>
    </div>
    <div class="acciones">
      <button>Ver más</button>
      <button>Agregar a mi pedido</button>
    </div>
  </div>
</template>

<script>
import Productshow from './products/Productshow'

export default {
  name: 'Product',
  props: [ 'product' ],
  components: {
    Productshow
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.product{
  width: 100%;
  float: left;
  padding: 15px 0;
}
.imagen{
  width: 100%;
  height: 125px;
  float:left;
  overflow: hidden;
  position: relative;
}
.imagen img{
  opacity: 1;
  object-fit: cover;
  object-position: center;
  border-radius: 10px 0 0 10px;
  width: 100%;
}
.texto{
  text-align: left;
}
h2{
  font-size: 15px;
}
h3{
 font-size: 14px;
}
h4{
 font-size: 14px;
}
</style>
