<template>
    <div id="app"></div>
    Hi, {{ name_first }}!

    <navigationLink url="https://www.google.de">
        <template v-slot:image>
            <img
                src="https://1000marken.net/wp-content/uploads/2021/01/Google-logo.png"
            />
        </template>

        Zum Profil</navigationLink
    >

    <!-- <a href="?seite=23" @click.prevent="test">Gehe zu Seite 23</a> -->
    <!-- <button @click="test">test</button> -->
    <todoList />
</template>

<script>
import todoList from "./components/todoList.vue";
import navigationLink from "./components/navigationLink.vue";

export default {
    name: "App",

    data: () => ({
        name_first: "Manuel",
    }),

    components: {
        todoList,
        navigationLink,
    },

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

img {
    height: 20px;
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
