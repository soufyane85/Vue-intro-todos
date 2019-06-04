<template>
    <div>
        <form @submit="addTodo"> 
            <input type="text" v-model="title" name="title" placeholder="Add Todo..." /> 
            <input type="submit" value="Submit" class="btn" />

        </form>
    </div>

</template>

<script>
import uuid from 'uuid';

export default {
    name : "AddTodo",
    methods: {
        addTodo(event){
            event.preventDefault();
            if( this.title ===""){
                return;
            }

            const newTodo = {
                id : uuid.v4(),
                title: this.title,
                completed: false
            }
            this.$emit('add-todo', newTodo);
        }
    },
    data(){
        return{
            title: ""
        }
    }
}
</script>

<style scoped>
    form{
        display: flex;
    }
    input[type= "text"]{
        flex: 10;
        padding: Spx;

    }
    input[type= "submit"]{
        flex: 2;
    }
</style>
