<template>
    <div class="todo-item" v-bind:class="{completed : todo.completed}">
        <p>
        <input type="checkbox" v-on:change="markComplete">
        <button v-on:click="$emit('del-todo', todo.id)" class="btn btn-danger">Delete</button>
        {{todo.title}}
        </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods : {
        markComplete() {
            this.todo.completed = !this.todo.completed
        }
    }
}
</script>

    <style scoped>
    .todo-item {
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }
    .todo-item:hover {
        opacity: 0.8;
    }
    .completed {
        text-decoration: line-through;
    }
    .btn {
        float: right;
    }
    .btn:hover {
        opacity: 0.5;
    }
    </style>


