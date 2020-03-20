<template>
  <div>
    <FormProducts :insertProduct="insertProduct" />
    <ProductList :products="products" />
  </div>
</template>

<script>
import FormProducts from './components/FormProducts.vue';
import ProductList from './components/ProductList.vue';

export default {
  data(){
    return{
      products: [
        {
          nome:'Teclado',
          descricao:'Teclado com alta velocidade',
        },
        {
          nome:'Mouse Razer',
          descricao:'Teclado com alta velocidade',
        },
        {
          nome:'Computador',
          descricao:'Computador core i5',  
        }
      ]
    };
  },
  components:{
    FormProducts,
    ProductList
  },
  methods:{
    insertProduct(prod){
      this.products = this.products.concat({
        nome: prod.nome,
        descricao: prod.descricao,
        quantidade: prod.quantidade,      
      })
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
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
