<template>
    <div class="display">
        <div v-for="todo in todos" v-bind:key="todo">
            <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"/>
        </div>
    </div>
</template>

<script>
import TodoItem from './TodoItem'

export default {
    name: "Todos",
    components:{
        TodoItem
    },
    props: ["todos"]
}
</script>

<style scoped>
    .display{
        border-bottom: 1px #1A3E7A solid;
    }
            
</style>