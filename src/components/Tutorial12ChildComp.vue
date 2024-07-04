
<script setup>
/**
 * defineProps()はコンパイル時マクロで、インポートなど不要
 * defineProps()の返すオブジェクトを介して、JavaScriptでアクセスできる
 */
const props = defineProps({
    msg: String
})
</script>

<template>
    <!-- propsは省略できる props.msg -->
    <h2>{{ msg || 'No props passed yet' }}</h2>
</template>