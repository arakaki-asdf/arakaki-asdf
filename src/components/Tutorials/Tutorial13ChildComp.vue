<script setup>
// 発行されるイベントを宣言
const emit = defineEmits(['response'])


function OnButton() {
    // 引数つきで発行
    emit('response', 'On Message')
}
</script>

<template>
    <button v-on:click="OnButton">On Message</button>
</template>