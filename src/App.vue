
<script setup>
  import { reactive } from 'vue'

  const counter = reactive({ count: 0 })
  const msg = "HELLO WORLD ";
  const rawHtml = `<span style="color: red">This should be red.</span>`;
  const dynamicId = 1000;
  const dynamicId2 = 2000;
  const isButtonDisabled=true;

  const objectOfAttrs = {
    id: 'container',
    class: 'wrapper',
    style: 'background-color: green'
  }
  let number = 0
  const ok = false
  const message = "hello world world world"
  const id = "my-id"
  const seen = true;
  const url = "https://www.google.co.jp/"

  function hello () {
    console.log("HELLO WORLD");
  }

  const clickOrFocusAttr = ["click", "focus"];
  // const clickOrFocusAttr = null;
  function doSomething() {
    console.log("do something");
  }
  function onSubmit(event) {
    console.log("onSubmit");
  }
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
    <button :disabled="isButtonDisabled" @click="counter.count++">{{ counter.count }}</button>
    <div v-bind:id="dynamicId">Message: {{ msg }}</div>
    <div :id="dynamicId2">Message: {{ msg }}</div>
    <div>text : {{ rawHtml }}</div>
    <div>text: <span v-html="rawHtml"></span></div>
    <div v-bind="objectOfAttrs">objectOfAttrs</div>

    {{ number + 1 }}
    {{ ok ? 'YES' : 'NO' }}
    {{ message.split('').reverse().join('') }}
    <div :id="`list-${id}`">list-{{ id }}</div>

    <p v-if="seen">Now you see me</p>
    <a v-bind:href="url">{{ url }}</a>
    <div><a v-on:click="hello">...</a></div>
    <div><a v-on:[clickOrFocusAttr[1]]="doSomething">{{ id }}</a></div>

    <form @:submit.prevent="onSubmit">onSubmit</form>
  </div>
</template>