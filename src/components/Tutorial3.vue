<script setup>
/**
 * https://ja.vuejs.org/tutorial/#step-3
 * イベントバインディング v-on
 * DOMイベントを購読することができます
 */
import { ref } from 'vue'
const count = ref(0)

function increment() {
    // コンポーネントの状態を更新する
    count.value++
}
</script>

<template>
    <!-- イベントバインド @clickで省略化 -->
    <!-- <button @click="increment">Count is : {{ count }}</button> -->
    <button v-on:click="increment">Count is : {{ count }}</button>
</template>

<style></style>