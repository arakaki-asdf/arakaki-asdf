<script setup>
/**
 * https://ja.vuejs.org/tutorial/#step-1
 * 宣言的レンダリング
 * reactive()やref()を使って宣言することで
 * 変更に対して動的なレンダリングをすることができる
 */
import { reactive, ref } from 'vue'
// reactive : オブジェクトに対して動作
const counter = reactive({ count: 0 })
// ref : 任意の値の型 (.valueで内部の値にアクセス)
const message = ref('Hello World')
</script>

<template>
    <!-- message(ref)は.valueを使用する必要がなく、簡潔に書ける -->
    <h1>{{ message }}</h1>
    <p>Count is: {{ counter.count }}</p>
</template>