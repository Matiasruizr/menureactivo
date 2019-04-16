<template>
  <div class="category">
    <h1>
      <a href="" class="imagen">
        {{ category.nombre }}
      </a>
    </h1>
    <Product v-for="product in category.products" v-bind:product="product" v-bind:key="product.id" />
  </div>
</template>

<script>
import Product from './Product.vue'

export default {
  name: 'Category',
  props: ['category'],
  components: {
    Product
  },
  data(){
    return{
      products: [ {}
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1{
    color: black;
  }
  a{
    color: black;
  }

</style>
