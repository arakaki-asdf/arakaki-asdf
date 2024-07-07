<script setup>
/**
 * shallowRefでwatch, watch getter, watchEffect
 * どれも追跡できない
 */
import { shallowRef, watch, watchEffect } from 'vue'
const data  = shallowRef({ text: "", id: 0 })

watch (data, () => {
    console.log(`watch : ${data.value.text}`)
})

watch (() => data.value.text, (text) => {
    console.log(`watch getter : ${text}`)
})

watchEffect(() => {
    console.log(`watchEffect : ${data.value.text}`)
})
</script>

<template>
    <input type="text" v-model="data.text" placeholder="input...">
    <p>text: {{ data.text }}</p>
</template>