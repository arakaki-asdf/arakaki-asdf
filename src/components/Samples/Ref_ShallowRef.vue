<script setup>
/**
 * shallowRefでwatch, watch getter, watchEffect
 * どれも追跡できない
 */
import { shallowRef, watch, watchEffect } from 'vue'
const data = shallowRef({ text: "", id: 0 })

watch (data, () => {
    console.log(`watch : ${data.value.text}`)
})

watch (() => data.value.text, (text) => {
    console.log(`watch getter : ${text}`)
})

watchEffect(() => {
    console.log(`watchEffect : ${data.value.text}`)
})

// プロパティではなく、オブジェクトの変更なら上記すべてで追跡されている
function changeButton() {
    data.value = { text: "change button", id: 100 }
}
</script>

<template>
    <input type="text" v-model="data.text" placeholder="input...">
    <p>text: {{ data.text }}</p>
    <button v-on:click="changeButton">changeButton</button>
</template>