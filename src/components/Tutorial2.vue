<script setup>
/**
 * https://ja.vuejs.org/tutorial/#step-2
 * 属性バインディング v-bind
 * 動的な値を属性にバインドする
 */
import { ref } from 'vue'
// 文字列をref(任意の型)で保持
// styleのクラス、id名を設定しておくとバインディングで設定可能
const titleClass = ref('title')
const titleId = ref('title-id')
</script>

<template>
    <!-- クラスを属性バインディング -->
    <h1 v-bind:class="titleClass">Make me red</h1>
    <!-- idを属性バインディング -->
    <h1 v-bind:id="titleId">Make me blue</h1>
    <!-- バインディングせず普通にクラス指定 -->
    <div class="gold">Make me blue</div>
</template>

<style>
.title {
    color: red;
}
#title-id {
    color: rgb(56, 56, 193);
}
.gold {
    color: gold;
}
</style>