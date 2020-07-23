<template>
    <div>
        <form @submit.prevent="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Add Todo...">
            <input type="submit" value="Submit" class="btn">
        </form>
            <input class="input2" type="text" v-model="description" name="description" placeholder="Add Description...">

    </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid'

export default {
    name: "AddTodo",
    data(){
        return{
            title: '',
            description: ''
        }
    },
    methods: {
        addTodo(e){
            e.preventDefault();
            const newTodo = {
                id: uuidv4(),
                title: this.title,
                completed: false,
                description: this.description
            }
            console.log(newTodo.id);
            this.title = '';
            this.description = '';
            // Send up to parent
            this.$emit('add-todo', newTodo);
        }
    }
}
</script>

<style scoped>

    form{
        display: flex;
    }
    input[type="text"] {
        flex: 10;
        padding: 5px;
    }
    input[type="submit"]{
        flex: 2;
    }

    .btn{
        display: inline-blick;
        border: none;
        background: #612FC2;
        color: #fff;
        padding: 7px 20px;
        cursor: pointer;
    }

    .input2{
        width: 100%;
        padding: 7px 20px;

    }

</style>