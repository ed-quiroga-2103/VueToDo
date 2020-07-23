<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{todo.title}}
            <button @click="$emit('del-todo', todo.id)" class="del">x</button>
        </p>
        <Description v-bind:todo="todo"/>
    </div>
</template>

<script>
import Description from "./Description"

export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete(){
            this.todo.completed = !this.todo.completed;
        }
    },
    components: {
        Description
    }
}
</script>

<style scoped>
    .todo-item{
        background: #2D4396;
        padding: 10px;
        border-bottom: 1px #1A3E7A solid;
    }

    .is-complete{
        text-decoration: line-through;
    }

    .del {
        background: red;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }

</style>