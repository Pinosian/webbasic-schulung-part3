<template>
  Add ToDo:
  <input v-model="todoName" @keydown.enter="addTodo(todoName)"/>
  <button @click="addTodo(todoName)" >Test</button>
  <ul class="todo-list">
    <li v-for="todo in todos" :key="todo.id" class="todo">
      <input type="checkbox" @click="checkTodo(todo.id)">
      {{todo.name}}
      <div class="delete">
        <button @click="deleteTodo(todo.id)"><i class="fas fa-times" /></button>
      </div>
    </li>
  </ul>
  <hr>
  Log:
  <ul class="todo-list">
<li v-for="todo in checkedToDos" :key="todo.id" class="todo">
  <input type="checkbox" @click="checkTodo(todo.id)" checked>
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
      checkedToDos: [],
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
      //if is necessary cause else -1 will be deleted:
      const todoIndex = this.todos.findIndex(todo => todo.id === id);
      if(todoIndex === -1){
        const checkedIndex = this.checkedToDos.findIndex(todo => todo.id === id);
        this.checkedToDos.splice(checkedIndex, 1);
      } else {
        this.todos.splice(todoIndex, 1);
      }
    },
     checkTodo(id) {
       const todoIndex = this.todos.findIndex(todo => todo.id === id);
       const toDo = this.todos[todoIndex];
       this.checkedToDos.push(toDo);
       this.deleteTodo(id);
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