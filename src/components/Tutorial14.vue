<script setup>
/**
 * https://ja.vuejs.org/tutorial/#step-14
 * スロット
 * 
 * 親コンポーネントから子コンポーネントへ渡すこと
 * 
 */
import { ref } from 'vue'
import Comp from './Tutorial14ChildComp.vue'
const msg = ref('from yet')
</script>

<template>
    <!-- 親コンポーネントから子に渡す1 -->
    <Comp>1. Message: {{ msg }}</Comp>

    <!-- 親コンポーネントから子に渡す2 -->
    <Comp>2. World World World</Comp>

    <!-- 親コンポーネントから渡さない場合 -->
    <Comp></Comp>
</template>