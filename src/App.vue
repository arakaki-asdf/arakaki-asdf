
<script setup>
// https://qiita.com/YuukiTerui/items/5fdb4819e8ceed2c5acf
import { shallowRef } from 'vue'
import Sidebar from './components/2Column/Sidebar.vue'
// import Main from './components/2Column/Main.vue'
import Tutorial1 from './components/Tutorials/Tutorial1.vue'
import Tutorial2 from './components/Tutorials/Tutorial2.vue'
import Tutorial3 from './components/Tutorials/Tutorial3.vue'
import Tutorial4 from './components/Tutorials/Tutorial4.vue'
import Tutorial5 from './components/Tutorials/Tutorial5.vue'
import Tutorial6 from './components/Tutorials/Tutorial6.vue'
import Tutorial7 from './components/Tutorials/Tutorial7.vue'
import Tutorial8 from './components/Tutorials/Tutorial8.vue'
import Tutorial9 from './components/Tutorials/Tutorial9.vue'
import Tutorial10 from './components/Tutorials/Tutorial10.vue'
import Tutorial11 from './components/Tutorials/Tutorial11.vue'
import Tutorial12 from './components/Tutorials/Tutorial12.vue'
import Tutorial13 from './components/Tutorials/Tutorial13.vue'
import Tutorial14 from './components/Tutorials/Tutorial14.vue'

const compList = [
  Tutorial1,
  Tutorial2,
  Tutorial3,
  Tutorial4,
  Tutorial5,
  Tutorial6,
  Tutorial7,
  Tutorial8,
  Tutorial9,
  Tutorial10,
  Tutorial11,
  Tutorial12,
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