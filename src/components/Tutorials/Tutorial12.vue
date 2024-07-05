<script setup>
/**
 * https://ja.vuejs.org/tutorial/#step-12
 * props
 * 子コンポーネントは、親コンポーネントからpropsを介して入力を
 * 受け取ることができます
 */
import { ref } from 'vue'
import ChildComp from './Tutorial12ChildComp.vue'
const greeting = ref("Hello from parent")
// const greeting = "Hello World"
</script>

<template>
    <!-- propsを子に渡す v-bind構文 -->
    <ChildComp v-bind:msg="greeting" />
</template>