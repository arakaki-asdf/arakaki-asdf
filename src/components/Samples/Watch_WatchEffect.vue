<script setup>
/**
 * watch, watch getter, watchEffectの使い分け
 * watchはオブジェクトのプロパティ変更を追跡できない
 */
import { ref, watch, watchEffect } from 'vue'
const data = ref({ text:"", id: 0 })
// const data  = shallowRef({ text: "", id: 0 })

// objectの変更を監視できない
watch (data, () => {
    console.log(`watch : ${data.value.text}`)
})

// () => の形でgetterにすれば、変更を監視できる
watch (() => data.value.text, (text) => {
    console.log(`watch getter : ${text}`)
})

// コールバック内のリアクティブな依存関係を自動的に追跡
watchEffect(() => {
    console.log(`watchEffect : ${data.value.text}`)
})
</script>

<template>
    <input type="text" v-model="data.text" placeholder="input...">
    <p>text: {{ data.text }}</p>
</template>