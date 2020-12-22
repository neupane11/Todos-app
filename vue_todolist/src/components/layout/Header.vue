<template>
    <header class="header">
        <h1>TodoList</h1>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    </header>
</template>

<script>
export default {
    name:"Header"
}
</script>

<style  scoped>
    .header {
        padding: 5px;
        text-align: center;
        background:black;
        color: white;
        font-size: 20px;
        width:100%;
}
</style>