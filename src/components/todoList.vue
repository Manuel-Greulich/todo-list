<template>
    <ul>
        <todoListItem
            v-for="todo in todos"
            :key="todo.id"
            :item="todo"
            @toggle="toggleListItem"
        />
    </ul>
</template>

<script>
import todoListItem from "./todoListItem.vue";

export default {
    name: "TodoList",

    components: {
        todoListItem,
    },

    data: () => ({
        todos: [
            { id: 1, finished: false, name: "Vue JS lernen" },
            { id: 2, finished: true, name: "Code beispiel üben" },
            { id: 3, finished: false, name: "Git Commit" },
            { id: 4, finished: true, name: "Ein weiteres Todo" },
        ],
    }),
    methods: {
        toggleListItem(el) {
            el.finished = !el.finished;
        },
    },
};
</script>

<style></style>
