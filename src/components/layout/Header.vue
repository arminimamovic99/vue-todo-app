<template>
    <header class="header">
        <h2>TodoList</h2>
    </header>
</template>

<script>
export default {
    name : "Header"
}
</script>

<style scoped>
    .header {
        background: #2d3436;
        color: #fff;
        text-align: left;
        padding: 10px;
    }
    h2:hover {
        opacity: 0.7;
    }
    .header a {
        color: #fff;
        padding-right: 5px;
    }
</style>

