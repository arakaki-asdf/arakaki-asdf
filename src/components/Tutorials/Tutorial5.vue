<script setup>
/**
 * https://ja.vuejs.org/tutorial/#step-6
 * 条件付きレンダリング v-if, v-else
 * 条件毎に表示、非表示切り替えなど可能
 */
import { ref } from 'vue'
const awesome = ref(true)

function toggle() {
    awesome.value = !awesome.value;
}
</script>

<template>
    <button v-on:click="toggle">Toggle</button>
    <!-- awesome === true -->
    <h1 v-if="awesome">Vue is awesome!</h1>
    <!-- else -->
    <h1 v-else>Oh no</h1>
</template>

<style></style>