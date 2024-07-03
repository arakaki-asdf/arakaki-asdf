
<script setup>
/**
 * https://ja.vuejs.org/tutorial/#step-8
 * 算出プロパティ computed
 * その計算の中で使用される他のリアクティブステート
 * を依存関係として追跡します。計算結果はキャッシュされて、
 * 依存関係が変更されると自動的に更新されます。
 */
import { ref, computed } from 'vue'
let id = 0

// model用
const newTodo = ref('')
// 算出用
const hideCompleted = ref(false)
const todos = ref([
  { id: id++, text: 'Learn HTML', done: true },
  { id: id++, text: 'Learn JavaScript', done: true },
  { id: id++, text: 'Learn Vue', done: false },
])

function addTodo() {
  todos.value.push({ id: id++, text: newTodo.value, done: false })
  newTodo.value = ''
}

function removeTodo(todo) {
  todos.value = todos.value.filter(x => x !== todo)
}

const filteredTodos = computed(() => {
  return hideCompleted.value
        ? todos.value.filter(x => !x.done)
        : todos.value
})
</script>

<template>
    <form v-on:submit.prevent="addTodo">
      <input v-model="newTodo" required placeholder="new todo">
      <button>Add Todo</button>
    </form>

    <ul>
      <li v-for="todo in filteredTodos" v-bind:key="todo.id">
        <input type="checkbox" v-model="todo.done">
        <span v-bind:class="{ done: todo.done }">{{ todo.text }}</span>
        <button v-on:click="removeTodo(todo)">X</button>
      </li>
    </ul>

      <button v-on:click="hideCompleted = !hideCompleted">
        {{ hideCompleted ? 'Show all' : 'Hide completed' }}
      </button>
</template>

<style>
.done {
  text-decoration: line-through;
}
</style>