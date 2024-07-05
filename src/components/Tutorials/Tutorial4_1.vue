<script setup>
/**
 * 双方向バインディングを簡略化 v-model
 * 
 * v-modelはテキスト入力だけではなく、チェックボックス、ラジオボタン、
 * セレクトボックスなどの他の入力タイプでも機能します
 */
import { ref } from 'vue'
const text  = ref('')
</script>

<template>
    <input v-model="text" placeholder="Type here">
    <p>{{ text }}</p>
</template>

<style></style>