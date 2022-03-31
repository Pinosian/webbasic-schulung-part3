<template>
  Add ToDo:
  <input v-model="todoName" @keydown.enter="addTodo(todoName)"/>
<button @click="addTodo(todoName)" >Test</button>
<ul>
  <li v-for="todo in todos" :key="todo.name">
    {{todo.name}}
  </li>
</ul>
</template>


<script>
export default {
  data() {
    return {
      todoName: ''
    }
  },
  inject: ['todos', 'addTodo'],
}

</script>