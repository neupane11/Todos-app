<template>
    <div>
        <div v-bind:key="elem.id" v-for="elem in todos" class="todo">
         <TodoItem v-bind:elem="elem" v-on:del-todo="$emit('del-todo',elem.id)"/>
        </div>
    </div>
</template>

<script>
import TodoItem from './TodoItem';

export default {
    name:"Todos",
   components:{
       TodoItem
   },
    props:["todos"]
}
</script>

<style scoped>
 
 
</style>