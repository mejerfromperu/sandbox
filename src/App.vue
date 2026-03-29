<script setup lang="ts">

import { ref } from "vue";


const testname = ref("test name ");


</script>

<template>
  <h1>You did it!</h1>

  <h1>{{ testname }}</h1>
  <p>
    Visit <a href="https://vuejs.org/" target="_blank" rel="noopener">vuejs.org</a> to read the
    documentation
  </p>
</template>

<style scoped></style>
