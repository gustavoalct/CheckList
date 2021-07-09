<template>
    <div align="center" id="app" class='container-fluid menu'>
        <div   class="container-sm interno">
          <br>
          <h1>CHECKLIST </h1>
          <br><br>
          <CriaTarefas> </CriaTarefas>
        </div>
  </div>
</template>


<script>
import CriaTarefas from './CriaTarefas.vue'
export default {
    components:{
      CriaTarefas,   
    }
}

</script>


<style >

.menu{
    background: #DDE7ED;
    min-height:100vh; /*  #DDE7EDEsticar tela até o fim  */
    padding-top:1% ;
    padding-bottom: 1%;
}

.menu .interno{
  background: white;
  min-height:100vh; 
}


</style>