<script setup>
import { ref, watch } from "vue";

const memberType = ref(0);
const emit = defineEmits(['response'])

const props = defineProps({
  names: Array
})
const names = props.names;
console.log(names)

async function watchMemberType() {
  // 切り替わったことを発火
  console.log("change member type")
  emit('response', memberType.value)
}

// 値変更を監視
watch(memberType, watchMemberType)

// for (const element of props.ary) {
//   console.log(`elem: ${element}`);
// }
</script>

<style scoped>
.box {
  height: 150vh;
}
.sidebar-label {
  display: block;
}
</style>

<template>
  <!-- <div class="box">
      <h2>サイドバー</h2>
      <ul>
          <li><a href="">目次</a></li>
          <li><a href="">タイトル</a></li>
          <li><a href="">lorem</a></li>
      </ul>
  </div> -->

  <div>
    <label class="sidebar-label" v-for="(name, index) in names" v-bind:key="name">
      <input type="radio" name="memberType" v-bind:value="index" v-model="memberType">{{ name }}
    </label>
    <!-- <label class="sidebar-label">
      <input type="radio" name="memberType" value="0" v-model="memberType">目次
    </label>
    <label class="sidebar-label">
      <input type="radio" name="memberType" value="1" v-model="memberType">タイトル
    </label>
    <label class="sidebar-label">
      <input type="radio" name="memberType" value="2" v-model="memberType">Lorem
    </label> -->

    <div>{{ memberType }}</div>
  </div>
</template>