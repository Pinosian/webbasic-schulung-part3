<template>
  <ToDoApp/> <br>
  So könnte der nächste Part aussehen, einfaches hinzufügen einer ToDo: <br><br>
  <ToDoPart1></ToDoPart1>
</template>

<script>
import ToDoApp from './components/ToDoApp.vue'
import ToDoPart1 from "@/components/ToDoPart1";

export default {
  name: 'App',
  data(){
    return {
    todos: [
      {name: 'Protokoll schreiben'},
      {name: 'Feedback geben'},
      {name: 'Projektbewerbung abschicken'}
    ]
  }
  },
  methods: {
    addTodo(name) {
      console.log(name);
      this.todos.push({name: name});
    }
  },
  provide() {
    return {
      todos: this.todos,
      addTodo: this.addTodo
    }
  },
  components: {
    ToDoApp, ToDoPart1
  }
}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');
@import url('https://pro.fontawesome.com/releases/v5.10.0/css/all.css');

* {
  font-family: Poppins;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
