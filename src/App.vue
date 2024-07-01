
<script setup>
  import Tutorial1 from './components/Tutorial1.vue'
  // import Tutorial2 from './components/Tutorial2.vue'
  // import Tutorial3 from './components/Tutorial3.vue'
  // import Tutorial4 from './components/Tutorial4.vue'
  import Tutorial5 from './components/Tutorial5.vue'
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
     <Tutorial5></Tutorial5>
  </div>
</template>