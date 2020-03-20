<template>
  <div class='produto'>
  <p><strong>{{product.nome}} </strong> | {{product.descricao}}</p>
  </div>
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
.produto{
  height: 200px;
  margin-top:10px;
  float: left;
  padding: 10px;
  border: solid 1px #cccccc ;
}
</style>
