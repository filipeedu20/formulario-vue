<template>
    <form @submit="onFormSubmit">
        <h1>Cadastro de Produtos </h1>
        <p>
            <label>Nome do Produto</label>
            <input type="text" v-model="nome">
            <p class='alert'>{{errorName}}<p>
        </p>
        <p>
            <label>Descrição</label>
            <input type="text" v-model="descricao">
            
        </p>
        <button type="submit"> Enviar </button>
    </form>
</template>

<script>
export default {
    data(){
        return{
           
            nome:"",
            descricao: "",
            isNameLimitExceeded: false,
            errorName:""           
        };
    },
    props:{
        insertProduct: Function
    },
    watch:{
        nome(){
            if(this.nome.length>15){
                this.isNameLimitExceeded = true;
                this.errorName = "O nome do produto não pode ultrapassar os 15 caracteres";
            }else{
                this.isNameLimitExceeded = false;
                this.errorName = "";
            }
        }
    },
    methods:{
        onFormSubmit(e) {
             e.preventDefault();

           if (this.isNameLimitExceeded) {
                return;
            }
           this.insertProduct({
               descricao: this.descricao,
               nome: this.nome
           });
       }
    }, 
}
</script>
<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  margin: 40px 0 0;
  color: #2c3e50;
}
.alert{
    color: brown;
}
</style>


