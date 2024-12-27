<script>
import ToDoItem from "@/components/ToDoItem.vue";
import ToDoForm from "@/components/ToDoForm.vue";
import uniqueId from "lodash.uniqueid";
import {ref} from 'vue';

export default {
    name: "app",
    components: {
        ToDoItem, ToDoForm,
    },
    data() {
        return {
            ToDoItems: [
                {id: uniqueId("todo-"), label: "Learn Vue", done: false},
                {id: uniqueId("todo-"), label: "Create a Vue project with the CLI", done: true},
                {id: uniqueId("todo-"), label: "Have fun", done: true},
                {id: uniqueId("todo-"), label: "Create a to-do list", done: false},
            ],
        };
    },
};

</script>

<template>
    <div id="app">
        <h1>My To-Do List</h1>
        <to-do-form></to-do-form>
        <ul>
            <li v-for="item in ToDoItems" :key="item.id">
                <to-do-item :label="item.label" :done="true" :id="item.id"></to-do-item>
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
