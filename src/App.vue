<template>
    <div id="app"></div>
    Hi, {{ name_first }}!

    <ul>
        <li
            v-bind:class="{ finishedTasks: todo.finished }"
            v-for="(todo, index) in todos"
            v-bind:key="todo.id"
        >
            <!-- attribute wird dynamisch gemacht mit v-bind und checked nur
            hinzugefügt wenn bedingung true ist  -->
            <input type="checkbox" v-bind:checked="todo.finished" />

            <a v-bind:href="'?id=' + todo.id">zeigen</a>
            {{ ++index }} {{ todo.name }}
        </li>
    </ul>

    <button @click="test">test</button>
</template>

<script>
export default {
    name: "App",

    data: () => ({
        name_first: "Manuel",
        todos: [
            { id: 1, finished: false, name: "Vue JS lernen" },
            { id: 2, finished: true, name: "Code beispiel üben" },
            { id: 3, finished: false, name: "Git Commit" },
            { id: 4, finished: true, name: "Ein weiteres Todo" },
        ],
    }),
    methods: {
        test() {
            alert("hi");
        },
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
