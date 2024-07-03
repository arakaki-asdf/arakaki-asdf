
<script setup>
/**
 * https://ja.vuejs.org/tutorial/#step-9
 * ライフサイクルとテンプレート参照
 * ref属性を使って、テンプレート参照が要求可能
 */
import { ref, onMounted } from 'vue'

// 要素にアクセス
// まだ存在されないためnullで初期化
const pElementRef = ref(null)


// ライフサイクルフック コンポーネントがマウントされるタイミング
onMounted(() => {
  // 要素のテキストコンテンツを書き換える
  pElementRef.value.textContent = "mounted!"
})
</script>

<template>
  <p ref="pElementRef">Hello</p>
</template>