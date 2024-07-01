<script setup>
/**
 * https://ja.vuejs.org/tutorial/#step-5
 * フォームバインディング
 * v-bindとv-onを一緒に使うことで、input要素に
 * 双方向バインディングを作成
 */
import { ref } from 'vue'
const text  = ref('')

function onInput(e) {
    // v-onハンドラーはネイティブDOMのイベントを
    // 引数として受け取る
    text.value = e.target.value
}
</script>

<template>
    <input v-bind:value="text"
        v-on:input="onInput"
        placeholder="Type here">
    <p>{{ text }}</p>
</template>

<style></style>