
<script setup>
/**
 * https://ja.vuejs.org/tutorial/#step-10
 * データをリアクティブに変更したい場合など、watch()を使用することで変更を監視できます
 * ボタンを押した時のtodoIdのインクリメント(変化)を監視して、fetchAPIでデータを更新してみる
 */
import { ref, watch } from 'vue'

const todoId = ref(1)
const todoData = ref(null)

async function fetchData() {
  todoData.value = null;
  const res = await fetch(`https://jsonplaceholder.typicode.com/todos/${todoId.value}`)
  todoData.value = await res.json()

  // yes/no watch https://ja.vuejs.org/guide/essentials/watchers
  // const res = await fetch('https://yesno.wtf/api')
  // todoData.value = (await res.json()).answer
}

fetchData()
// watch関数はrefを直接扱えます
watch(todoId, fetchData)
</script>

<template>
  <p>Todo id: {{ todoId }}</p>
  <button v-on:click="todoId++" v-bind:disabled="!todoData">Fetch next todo</button>
  <p v-if="!todoData">Loading...</p>
  <pre v-else>{{ todoData }}</pre>
</template>