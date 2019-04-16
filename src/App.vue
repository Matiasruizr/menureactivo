<template>
  <div id="app">
    <!-- Trae todas las categorías del menu -->
    <Category v-for="category in categories" 
    v-bind:category="category" v-bind:key="category.id" />
  </div>
 </template>

<script>

import Category from './components/Category.vue'

function getMenu(){
  // Traemos la api de esta url
  return fetch('https://acomerapp.cl/menu/show.json?id=10')
    //Fetch nos devuelve una promesa con la respuesta 
    .then(res =>res.json() )
    .then(json => json.categories)
    .catch(function(error) {
      console.log('Looks like there was a problem: \n', error)
    })
}

export default {
  name: 'app',
  components: {
    Category
  },
  data() {
    return{
      categories: []
    }
  }, 
  mounted: function() {
    const self = this
    getMenu()
    .then(function (categories)  {
      self.categories = categories
      console.log(categories)
    })
  } 
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
