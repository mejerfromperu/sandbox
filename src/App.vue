<script setup lang="ts">

import { ref } from "vue";



const testname = ref("test name ");
const counter = ref<number>(0);


function add() : number {
  counter.value += 1;
  return counter.value;
}




</script>

<template>
  <h1>You did it!</h1>

  <h1>{{ testname }}</h1>
  <button @click="add">Add</button>
  <p>counter: {{ counter }}</p>
  <p>
    Visit <a href="https://vuejs.org/" target="_blank" rel="noopener">vuejs.org</a> to read the
    documentation
  </p>
</template>

<style scoped>

.button {
  background-color: #42b983;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}

</style>
