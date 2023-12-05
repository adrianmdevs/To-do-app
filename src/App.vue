<template>
  <img alt="to-do logo" src="./assets/list.png">
  <div id="app">
    <h1>My To-Do List</h1>
    <ul>
      <li v-for="item in ToDoItems" :key="item.id">
        <to-do-item label="item.label" :done="item.done"></to-do-item>
      </li>
    </ul>
  </div>
</template>

<script>
import uniqueId from 'lodash.uniqueid';
 import ToDoItem from './components/ToDoItem.vue';
 


export default {
  name: 'App',
  components:{
    ToDoItem,
  },
  data(){
    return {
      ToDoItems:[
        { id:uniqueId("to-do"),label: "Learn Vue", done: false},
        { id:uniqueId("to-do"),label: "Create a Vue project with the CLi", done: true},
        { id:uniqueId("to-do"),label: "Have fun", done: true},
        { id:uniqueId("to-do"),label: "Create a to-do list", done: false},

      ],
    };
  },
 
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
