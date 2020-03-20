<template>
    <form @submit="onFormSubmit">
        <p>Cadastro de Produtos </p>
        <p>
            <label>Nome do Produto</label>
            <input type="text" v-model="nome">
            {{errorName}}
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
        desc_produto(){
            if(this.descricao.length>15){
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
               nome: this.nome,
               quantidade:this.quantidade
           });
       }
    }, 
}
</script>

