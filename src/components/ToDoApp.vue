<template>
  <h2>This is my To-Do List</h2>
  <!--
        Mehrere ToDos einfügen.
        Überlegt euch auch unterschiedliche Inhalte für die ToDos
        Baut in eines der ToDos einen Link auf eine Seite eurer Wahl ein!
        Markiert ein ToDo eurer Wahl fett!
        (3 min)
     -->
  <div class="todo-list">
    <div class="todo">
      <div class="check">
        <button><i class="fas fa-check"></i></button>
      </div>

      <div class="content">
        <strong>Protokoll schreiben</strong>
      </div>

      <div class="delete">
        <i class="fas fa-times"></i>
      </div>
    </div>
    <div class="todo">
      <div class="check">
        <button><i class="fas fa-check"></i></button>
      </div>

      <div class="content">
        <span style="color: red">Programmieren lernen</span>
      </div>

      <div class="delete">
        <i class="fas fa-times"></i>
      </div>
    </div>
    <div class="todo">
      <div class="check">
        <button><i class="fas fa-check"></i></button>
      </div>

      <div class="content">
        <a href="https://hc-central.hanseaticconsulting.de"
        >Projektbewerbung abschicken</a
        >
      </div>

      <div class="delete">
        <i class="fas fa-times"></i>
      </div>
    </div>
    <button class="add">Add | +</button>
  </div>
</template>

<script>
export default {
  name: 'ToDoApp',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');
@import url('https://pro.fontawesome.com/releases/v5.10.0/css/all.css');


* {
  font-family: Poppins;
}

button.add {
  border: 1px solid lightgrey;
  box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.15);
  background-color: #5faaff;
  border-radius: 5px;
  padding: 5px 10px;
  margin-top: 20px;
  transition: 700ms;
}

.check,
.content,
.delete {
  padding: 5px;
}

.check i {
  opacity: 0;
}

.check button {
  border-radius: 100%;
  width: 1.5rem;
  height: 1.5rem;
  background-color: none;
  border: 2px solid grey;
  padding: 0px;
}

.todo {
  display: grid;
  grid-template-columns: max-content 1fr max-content;
}

.todo-list {
  display: flex;
  flex-direction: column;
}

body {
  display: flex;
  flex-direction: column;
}

/* --- NEW --- */

button.add:hover {
  background-color: #000f28;
  transition: 700ms;
  color: white;
}

.check button:hover {
  background-color: white;
  border: none;
  transition: 600ms;
}

.check button:hover i {
  opacity: 0.5;
  transition: 700ms;
}

.check button:focus i {
  opacity: 1;
  transition: 700ms;
}

.check button:focus {
  background-color: white;
  border: none;
}

.check button:visited {
  opacity: 0;
  transition: 400ms;
}

</style>
