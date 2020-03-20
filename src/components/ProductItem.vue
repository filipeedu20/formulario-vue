<template> 
  <p>{{product.nome}} - {{product.quantidade}} -  {{product.descricao}}</p>
</template>

<script>
export default {
  name:'ProductList',
  props: {
    product: Object
  },
}
</script>

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
