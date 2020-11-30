<template>
    <div>
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Название задачи">
            <input type="submit" value="Добавить" class="btn">
        </form>
    </div>
</template>

<script>
export default {
    name: 'AddTodo',
    methods: {
        addTodo(e) {
            e.preventDefault();

            const newTodo = {
                title: this.title,
                completed: false
            };

            this.$emit('add-todo', newTodo);

            this.title = '';
        }
    },
    data() {
        return {
            title: ''
        }
    }
}
</script>

<style scoped>
    form {
        display: flex;
    }

    input[type="text"] {
        flex: 10;
        padding: 5px;
    }

    input[type="submit"] {
        flex: 2;
    }
</style>