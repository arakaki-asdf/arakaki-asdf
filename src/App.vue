
<script setup>
  // import Tutorial1 from './components/Tutorial1.vue'
  import Tutorial from './components/Tutorials/Tutorial14.vue'
</script>

<style scoped>
  button {
    width: 150px;
    height: 30px;
  }
  .wrapper {
    font-size: 30px;
  }
  a.focus {
    background-color: lightblue;
  }
</style>

<template>
  <div id="app">
    <!-- <ChildComponent></ChildComponent> -->
     <Tutorial></Tutorial>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  height: 100vh;
}

.sidebar {
  overflow: hidden;
  flex: 1;
}

.sidebar:hover {
  overflow: auto;
}

.main {
  overflow: auto;
  flex: 2;
}

.box {
  height: 150vh;
}
</style>