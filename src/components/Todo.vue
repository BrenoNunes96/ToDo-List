<template>
<div class="container">

<h1>TO DO LIST</h1>
  
  <input class="input" v-model="novaTarefa" @keyup.enter="adicionarTarefa" placeholder="Adicione aqui">
  <button class="botao2" @click="adicionarTarefa"> adicionar Tarefa</button>
  <ul>
    <li class="lista" v-for="(tarefa, indice) in tarefas" :key="indice">
      {{ tarefa }}
      <button class="botao1" @click="removerTarefa(indice)">Remover</button>
    </li>
  </ul>
</div>


</template>
    
<script>
export default{

data() {
        return{
      novaTarefa: '',
      tarefas: []
    }},
    methods: {
      adicionarTarefa: function () {
        if (this.novaTarefa.trim() !== '') {
          this.tarefas.push(this.novaTarefa.trim());
          this.novaTarefa = '';
        }
      },
      removerTarefa: function (indice) {
        this.tarefas.splice(indice, 1);
      }
    }
  };

</script>

<style>
.input{
    height: 50px;
    width: 300px;
    border-radius: 15px;

}
.container{
margin-bottom: 500px;
}

h1{
text-align: center;
}

.botao2{
    margin-left: 20px;
}
 



</style>