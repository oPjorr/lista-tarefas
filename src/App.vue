<template> 
  <section>
    <cabecalho :valor ="titulo"/>
    <div class="container">
      <div class="input-group">
        <input @keyup.enter="adicionarTarefa" v-model="novaTarefa" type="text">
        <span class="input-group-btn">
          <button @click="adicionarTarefa" class="btn btn-primary">Adicionar tarefa</button>
        </span>
      </div>
      <ul>
        <li v-for="(tarefa, index) in tarefas" :key="index" :class="{ 'removed': tarefa.checked }">
          <input type="checkbox" v-model="tarefa.checked">
          <label> {{ tarefa.titulo }} </label>
        </li>  
      </ul>
      <footer>
        <em>Altere aqui o título da sua lista de tarefas</em>
        <input v-model="titulo" type="text" />
      </footer>
    </div>
  </section>
</template>

<script>
  import cabecalho from '@/components/cabecalho'; 
  export default {
    name: 'App',
    components: { cabecalho },
    data() {
      return {
        titulo: "Minha lista de tarefas", 
        novaTarefa: '',
        tarefas: [
          { titulo: "Estudar", checked: false },
          { titulo: "Programar", checked: true },
        ]  
      };
    },
    methods: {
      adicionarTarefa() {
        this.tarefas.push({
          titulo: this.novaTarefa,
          checked: false,
        });
        this.novaTarefa = "";
      }
    }
  }
</script>

<style>
.container {
  width: 40%;
  padding-top: 50px;
  margin: 20px auto 0 auto;
}

ul li {
  list-style: none;
}

.removed {
  color: red;
}

.removed label {
  text-decoration: line-through;
}
</style>