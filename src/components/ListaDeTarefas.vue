<script setup>
const props = defineProps(["tarefas"]);
</script>

<template>
  <ul class="list-group mt-4">
    <li v-if="props.tarefas.length === 0" class="list-group-item">Não possui tarefas</li>
    <li class="list-group-item" v-else v-for="tarefa in props.tarefas">
      <input @change="(evento) => (tarefa.finalizado = evento.target.checked)" :checked="tarefa.finalizado" :id="tarefa.titulo" type="checkbox" />
      <label :class="{ done: tarefa.finalizado }" class="ms-3" :for="tarefa.titulo">{{ tarefa.titulo }} </label>
    </li>
  </ul>
</template>

<style scoped>
.done {
  text-decoration: line-through;
  color: rgb(5, 209, 5);
}
</style>
