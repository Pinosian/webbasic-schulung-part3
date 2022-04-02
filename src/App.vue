<template>
  <ToDoApp/> <br>
  So könnte der nächste Part aussehen, einfaches hinzufügen einer ToDo: <br><br>
  <ToDoPart1></ToDoPart1>
  <br><br>
  <ToDoPart2></ToDoPart2>
  <br><br>
  <ToDoPart3></ToDoPart3>
</template>

<script>
import ToDoApp from './components/ToDoApp.vue';
import ToDoPart1 from "@/components/ToDoPart1";
import ToDoPart2 from "@/components/ToDoPart2";
import ToDoPart3 from "@/components/ToDoPart3";

export default {
  name: 'App',
  data(){
    return {
    todos: [
      {id: 1, name: 'Protokoll schreiben'},
      {id: 2, name: 'Feedback geben'},
      {id: 3, name: 'Projektbewerbung abschicken'}
    ]
  }
  },
  provide() {
    return {
      todos: this.todos,
    }
  },
  components: {
    ToDoApp, ToDoPart1, ToDoPart2, ToDoPart3
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
