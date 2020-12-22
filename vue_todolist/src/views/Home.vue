<template>
  <div id="app" >
    <b-conatiner>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
    </b-conatiner>
  </div>
</template>

<script>
//import Header from '../components/layout/Header'
import Todos from '../components/Todos';
import AddTodo from '../components/AddTodo';

export default {
  name: 'Home',
  components: {
    //Header,
    Todos,
    AddTodo
  },
 
 data() {
   return{
    todos: [
      {
        id:1,
        title:'take trash',
        completed:false
      },
      {
        id:2,
        title:'eat',
        completed:false
      },
      {
        id:3,
        title:'gym',
        completed:false
      }
    ]
   }
  },
  methods:{
    deleteTodo(id){
      this.todos=this.todos.filter(elem=>elem.id!==id);
    },
    addTodo(newTodo){
      this.todos=[...this.todos,newTodo];
    },

  }
}
</script>

<style> 
* {
  box-sizing: border-box;
  margin:0;
  padding-left:40px;
  padding-right: 40px;
  
  

}
body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
  
  
}
.home{
  position: fixed;
  top: 50%;
  left: 50%;
  /* bring your own prefixes */
  transform: translate(-50%, -50%);
}
</style>

