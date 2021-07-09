<template lang="">
    <div >
        
        <br>
        <button class="btn btn-info btn-md  interno2" v-on:click="Mostrar" type="submit" >Mostrar Tarefas</button>
        <br>  <br> 
        
       <div class=" interno " align="center" v-if="mostrar==true" >
            <ul class="lista">
                <li v-if="dados.length == 0">
                    <br> 
                    <h4> Não há tarefas.  &#9873;</h4>
                </li>
                <li v-else class="listar" v-for="(item, index) in dados"  :key="item.id">
                    <h4> {{ index + 1 }} &#10139; {{ item.tarefa }} </h4> 
                    <button v-on:click="ExcluirItem(index)"  type="submit" class="btn btn-danger btn-md botao2">  Excluir  </button>
                    <label class="btn btn-success btn-md botao2">
                        <input  type="checkbox" autocomplete="off"> Executada
                    </label>
                    
                    <br><br>
                </li>
                <br>
                <button  v-on:click="Fechar" type="submit" class="btn btn-dark btn-sm btn-block">Esconder tarefas</button>
                <br><br>
            </ul>     
        </div>
    </div>

</template>


<script>

export default {
    props:['dados'],

    data(){
        return{
            mostrar:false,
        }
        
    },
    
    methods:{
        Mostrar(){
        this.mostrar=true
        },
        Fechar(){
            this.mostrar=false
        },
        ExcluirItem(index){
            /* Excluir item */
            console.log(index),
             this.dados.splice(index,1); 
        }
    }
}
</script>

<style> 
.menu .interno{
    background: white;
    
    border-radius: 10px;
}


.menu .interno .botao2{
    margin-left: 0.5%;
    margin-right: 0.5%;
}
.menu .interno .lista{
    background: #D2FFDA ;
    border-radius: 2%;
    padding-left: 4%;
    padding-right: 4%;
    margin: 2%;
}
.menu .interno .lista .listar .botao2{ 
    margin-left: 1%;
    margin-right: 1%;
    
}   

</style>