<template>

    <div align="center"> 
         <div >
            <button  v-on:click="CriarItem" type="submit" class="btn btn-success btn-md "> Criar uma Nova Tarefa</button> 
        </div>
        <br>
        <div v-if="criar==true"> 
            <label  class="form-label "><h3 class="texto"> Escreva uma tarefa </h3> </label>
            <input placeholder="Escreva a tarefa" type="text"  v-model="tarefa" class="form-control">
            <br> 
            <br> 
            <div v-if="tarefa==''" >
                <h6> 	&#9998; Campo vazio, escreva uma tarefa 	&#9998; </h6>
            </div>
            <div v-else >
                <button class="btn btn-success btn-md" v-on:click="additem" type="submit" >Criar tarefa</button>
            </div> 
        </div>
        <br>
        <hr>
        <mostrar-excluir v-bind:dados="itens"> </mostrar-excluir>
    </div>

</template>


<script>
import Excluir from './Excluir.vue'

export default {
    components:{
        'mostrarExcluir':Excluir
    },
    
    data(){
        return{  
           itens:[
            ],
            tarefa:"",
            //mostrar:false,
            criar:false
        }
    },

    methods: {
     additem(){
         this.itens.push({
             tarefa:this.tarefa
         })
         this.tarefa='',
         this.criar=false
     },  

     CriarItem(){
         this.criar=true
     }
    }
}
</script>


