<template>
    <div class="todo-item" v-bind:class="{'is-complete':elem.completed}">
        <h3>
            <input type="checkbox" v-on:change="markComplete">
            {{elem.title}}
            <button @click="$emit('del-todo',elem.id)" class="btn">x</button>
            </h3>
    </div>
</template>

<script>
export default {
    name:"TodoItem",
    props:["elem"],
    methods:{
        markComplete(){
            this.elem.completed=!this.elem.completed;
        }
    }
}
</script>

<style  scoped>
    .todo-item{
        background:grey;
        padding:10px;
        border-bottom:1px black dotted;
        margin:10px;
        border: 1px solid blue;
        border-radius: 10px;
        width:850px
        
    }

    .is-complete{
        text-decoration: line-through red;
        
    }
    .btn {
        background-color:blue; 
        border: none; 
        color: white; 
        padding: 2px 5px; 
        font-size: 16px; 
        cursor: pointer;
        float:right 
        }

        /* Darker background on mouse-over */
        .btn:hover {
        background-color: red;
        }
</style>