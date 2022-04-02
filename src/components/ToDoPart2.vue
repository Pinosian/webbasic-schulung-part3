<template>
  Add ToDo:
  <input v-model="todoName" @keydown.enter="addTodo(todoName)"/>
  <button @click="addTodo(todoName)" >Test</button>
  <ul class="todo-list">
    <li v-for="todo in todos" :key="todo.name" class="todo">
      <input type="checkbox">
      {{todo.name}}
      <div class="delete">
        <button @click="deleteTodo(todo.id)"><i class="fas fa-times" /></button>
      </div>
    </li>
  </ul>
</template>


<script>
export default {
  data() {
    return {
      todoName: '',
      checked: false
    }
  },
  methods: {
    addTodo(name) {
      const newTodo = {
        id: new Date().toISOString(),
        name: name
      };
      this.todos.push(newTodo);
    },
    deleteTodo(id) {
      const todoIndex = this.todos.findIndex(todo => todo.id === id);
      this.todos.splice(todoIndex, 1);
    }
  },
  inject: ['todos'],
}

</script>

<style scoped>
.todo {
  display: grid;
  grid-template-columns: max-content 1fr max-content;
}

.todo-list {
  display: flex;
  flex-direction: column;
}

.check,
.content,
.delete {
  padding: 5px;
}
</style>