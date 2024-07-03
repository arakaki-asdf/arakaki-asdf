<script setup>
/**
 * https://ja.vuejs.org/tutorial/#step-7
 * リストレンダリング v-for
 * 配列を基にした要素のリストをレンダリング
 */
import { ref } from 'vue'
// git each todo a unique id
let id = 0;

const newTodo = ref('')
const todos = ref([
    { id: id++, text: 'Learn HTML' },
    { id: id++, text: 'Learn JavaScript' },
    { id: id++, text: 'Learn Vue' },
])

function addTodo() {
    todos.value.push({ id: id++, text: newTodo.value })
    newTodo.value = ''
}
function removeTodo(todo) {
    todos.value = todos.value.filter(x => x.id !== todo.id);
}
</script>

<template>
    <form v-on:submit.prevent="addTodo">
        <input v-model="newTodo" required placeholder="new todo">
        <button>Add Todo</button>
        <div>{{ newTodo }}</div>
    </form>

    <ul>
        <!-- key属性 -->
        <!-- v-for の key 属性は、可能な場合は必ず指定することが推奨されます -->
        <!-- keyで並び替えしてる？ -->
        <li v-for="todo in todos" v-bind:key="todo.id">
            {{ todo.text }}
            <button v-on:click="removeTodo(todo)">X</button>
        </li>
    </ul>
</template>

<style></style>