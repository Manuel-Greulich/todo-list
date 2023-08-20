<template>
    <li v-bind:class="{ finishedTasks: item.finished }">
        <input type="checkbox" v-bind:checked="item.finished" />

        <!-- <a v-bind:href="'?id=' + item.id">zeigen</a> -->
        <button @click="toggleItem">Toggle</button>
        {{ item.name }}
    </li>
</template>

<script>
export default {
    name: "todoListItem",

    props: ["item"],

    methods: {
        toggleItem() {
            this.$emit("toggle", this.item);
        },
    },
};
</script>

<style>
button {
    cursor: pointer;
}
</style>
