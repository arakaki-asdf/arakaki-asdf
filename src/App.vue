
<script setup>
import { shallowRef, ref } from 'vue'
import Sidebar from './components/2Column/Sidebar.vue'
// import Main from './components/2Column/Main.vue'
import Tutorial1 from './components/Tutorials/Tutorial1.vue'
import Tutorial2 from './components/Tutorials/Tutorial2.vue'
import Tutorial3 from './components/Tutorials/Tutorial3.vue'
import Tutorial13 from './components/Tutorials/Tutorial13.vue'
import Tutorial14 from './components/Tutorials/Tutorial14.vue'

const compList = [
  Tutorial1,
  Tutorial2,
  Tutorial3,
  Tutorial13,
  Tutorial14,
]
// TODO: refからshallowRefに変えるとエラーが出なくなった。後で調べる
const currentComp = shallowRef(Tutorial1);

function sideResponse(index) {
  currentComp.value = compList[index];
}

const names = compList.map(x => x.__name);
// console.log(names)
</script>

<style scoped>
.container {
  display: flex;
    height: 100vh;
  }

.main {
    overflow: auto;
    flex: 2;
}

.sidebar {
  overflow: hidden;
  flex: 1;
}

.sidebar:hover {
  overflow: auto;
}

</style>

<template>
  <div id="app">
    <div class="container">
      <div class="sidebar">
        <Sidebar 
          v-bind:names="names"
          v-on:response="sideResponse"></Sidebar>
      </div>

      <div class="main">
        <!-- <KeepAlive></KeepAlive> -->
        <component :is="currentComp"></component>
        <!-- <Main></Main> -->
      </div>
    </div>
  </div>
</template>
