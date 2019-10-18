<template>
    <div>
        <form v-on:submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Add Task...">
            <input type="submit" value="Add" class="btn">
        </form>
    </div>
</template>

<script>
import uuid from 'uuid';
export default {
    name: "AddTodoForm",
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();
            const newTodo = {
                id: uuid.v4(),
                title: this.title,
                completed: false
            }
            this.$emit('add-todo', newTodo);

            this.title = ''
        }
    }
}
</script>

<style scoped>
    form {
        display: flex;
        height: 50px;
    }
    input[type="text"] {
        flex: 10;
        padding: 5px;
    }
    input[type="submit"] {
        flex: 2;
        padding: 5px;
    }
    .btn {
        background: #0984e3;
        color: white;
        border: none;
    }
    .btn:hover {
        opacity: 0.7;
    }
</style>


