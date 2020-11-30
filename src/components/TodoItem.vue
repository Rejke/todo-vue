<template>
    <div class="todo-item">
        <p>
            <input type="checkbox" v-on:change="markComplete" :checked="todo.completed">
            <span class="ml-1" v-bind:class="{'completed': todo.completed}">{{todo.title}}</span>
            <button @click="$emit('del-todo', todo.id)" class="del">x</button>
        </p>
    </div>
</template>

<script>
export default {
    name: 'TodoItem',
    methods: {
        markComplete() {
            this.todo.completed = !this.todo.completed;
        }
    },
    props: ["todo"]
}
</script>

<style scoped>
    .ml-1 {
        margin-left: 4px;
    }

    .todo-item {
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px dotted #ccc;
    }

    .completed {
        text-decoration: line-through;
    }

    .del {
        background: #ff0000;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>