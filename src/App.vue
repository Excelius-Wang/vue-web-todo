<script setup>
import ToDoItem from "@/components/ToDoItem.vue";
import uniqueId from "lodash.uniqueid";
import { ref } from 'vue';

// 创建 ref 来管理状态
const ToDoItems = ref([
    { id: uniqueId("todo-"), label: "Learn Vue", done: false },
    {
        id: uniqueId("todo-"),
        label: "Create a Vue project with the CLI",
        done: true,
    },
    { id: uniqueId("todo-"), label: "Have fun", done: true },
    { id: uniqueId("todo-"), label: "Create a to-do list", done: false },
]);
</script>

<template>
    <div id="app">
        <h1>To-Do List</h1>
        <ul>
            <li>
                <to-do-item label="My ToDo Item" :done="true"></to-do-item>
            </li>
        </ul>
    </div>
</template>


<style scoped>
header {
    line-height: 1.5;
}

.logo {
    display: block;
    margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
    header {
        display: flex;
        place-items: center;
        padding-right: calc(var(--section-gap) / 2);
    }

    .logo {
        margin: 0 2rem 0 0;
    }

    header .wrapper {
        display: flex;
        place-items: flex-start;
        flex-wrap: wrap;
    }
}
</style>
