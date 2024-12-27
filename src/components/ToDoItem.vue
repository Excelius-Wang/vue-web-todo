<script setup>
import uniqueId from "lodash.uniqueid";

const props = defineProps({
    props: {
        label: {required: true, type: String},
        done: {default: false, type: Boolean}
    },
    data() {
        return {
            isDone: this.done,
            id: uniqueId("todo-"),
        };
    },
});
</script>

<template>
    <div>
        <input type="checkbox" :id="id" :checked="isDone"/>
        <label :for="id">{{ label }}</label>
    </div>
</template>

<style scoped>

</style>