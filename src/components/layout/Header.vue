<template>
    <header>
        <h1>VueTodo</h1>
        <div id="nav">
            <router-link to="/">Главная</router-link> |
            <router-link to="/about">Информация</router-link>
        </div>
    </header>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style scoped>
    header {
        background: #333;
        color: #fff;
        text-align: center;
        padding: 10px;
    }

    header a {
        color: #fff;
        padding-right: 5px;
        text-decoration: none;
    }
</style>