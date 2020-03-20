<template> 
   <div>
     <ul>
       <li v-for="product in products" :key="product.descricao">
          <ProductItem :product="product" /> 
       </li>
     </ul>
     Total de Produtos: {{totalItens}}
   </div>
</template>

<script>
import ProductItem from './ProductItem'

export default {
  name: 'ProductList',
  props:{
    products: Array
  },
  components:{
    ProductItem
  },
  computed:{
    totalItens(){
      return this.products.length;
    }
  }
}
</script>
