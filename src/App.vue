<template>
    <div id="app"></div>
    Hi, {{ name_first }}!

    <button @click="test">test</button>
    <todoList />
</template>

<script>
import todoList from "./components/todoList.vue";

export default {
    name: "App",

    data: () => ({
        name_first: "Manuel",
    }),

    methods: {
        test() {
            alert("hi");
        },
    },

    components: {
        todoList,
    },
};
</script>

<style>
body {
    background-color: lightgrey;
}

.finishedTasks {
    text-decoration: line-through;
}
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
