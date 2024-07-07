<script setup>
/**
 * https://ja.vuejs.org/tutorial/#step-13
 * 子から親へのイベント発行
 * 
 * 子はemit()でイベントを発行できます
 * 親はv-onを使って子が発行するイベントを購読できます
 */
import { ref } from 'vue'
import ChildComp from './Tutorial13ChildComp.vue'
const childMsg  = ref('No child msg yet')
</script>

<template>
    <!-- propsを子に渡す v-bind構文 -->
    <ChildComp v-on:response="(msg) => childMsg = msg" />
    <h3>{{ childMsg || "no message." }}</h3>
</template>