<template>
    <div>
      <h1>ToDo List</h1>
      <input v-model="newTodo" @keyup.enter="addTodo" placeholder="Add a new task" />
      <button @click="addTodo">Add</button>
      <ul>
        <li v-for="(todo, index) in todos" :key="index">
          <span :class="{ done: todo.done }" @click="toggleDone(index)">{{ todo.text }}</span>
          <button @click="removeTodo(index)">Remove</button>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newTodo: '',
        todos: []
      };
    },
    methods: {
      addTodo() {
        if (this.newTodo.trim() !== '') {
          this.todos.push({ text: this.newTodo, done: false });
          this.newTodo = '';
        }
      },
      toggleDone(index) {
        this.todos[index].done = !this.todos[index].done;
      },
      removeTodo(index) {
        this.todos.splice(index, 1);
      }
    }
  };
  </script>
  
  <style scoped>
  h1 {
    font-size: 24px;
    margin-bottom: 20px;
  }
  
  input {
    padding: 10px;
    font-size: 16px;
    margin-right: 10px;
  }
  
  button {
    padding: 10px;
    font-size: 16px;
    cursor: pointer;
  }
  
  ul {
    list-style-type: none;
    padding: 0;
  }
  
  li {
    display: flex;
    align-items: center;
    margin-bottom: 10px;
  }
  
  li span {
    flex-grow: 1;
    cursor: pointer;
  }
  
  li span.done {
    text-decoration: line-through;
    color: gray;
  }
  </style>