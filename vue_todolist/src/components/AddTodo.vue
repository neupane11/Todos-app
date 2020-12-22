<template>
    <div>
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Add item" class="entertext">
            <input type="submit" value="Add" class="btn">
        </form>
    </div>    
</template>

<script>
import uuid from 'uuid'
export default {
    name:"AddTodo",
    data(){
        return{
            title:''
        }

    },
    methods:{
        addTodo(e){
            e.preventDefault();
            const newTodo={
                id: uuid.v4(),
                title:this.title,
                completed:false,
                

            }
            //send up to parent
            this.$emit('add-todo',newTodo);
            this.title=''
        }
    }
}
</script>


<style  scoped>
    .btn{
        
        background-color: green;
        color:white;
        padding: 10px;
        cursor: pointer;
        width:50px;
        border:1px solid red;
        border-radius: 3px;
        
    }
    .entertext{
        width:800px;
        border: 5px solid red;
        margin-left: 10px;
        padding:10px;
    }
</style>














