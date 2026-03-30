<script setup lang="ts">

import { reactive, ref } from "vue";

  const store = reactive({
  selectedId: 0,
  selectedTitle: "",
  selectedCompany: "",
  selectedLocation: "",
  selectedDescription: "",
  job: {
    id: 0,
    title: "",
    company: "",
    location: "",
    description: "",
  },
  
});

export type Job = {
  id: number;
  title: string;
  company: string;
  location: string;
  description: string;
};

const jobs = ref<Job[]>([]);

function onClickJob() {
  const newJob: Job = {
    id: store.selectedId,
    title: store.selectedTitle,
    company: store.selectedCompany,
    location: store.selectedLocation,
    description: store.selectedDescription,
  };

  jobs.value.push(newJob);

  store.selectedId = 0;
  store.selectedTitle = "";
  store.selectedCompany = "";
  store.selectedLocation = "";
  store.selectedDescription = "";
}

const counter = ref(0);
const testname = "Vue 3 + TypeScript";

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
  <form @submit.prevent class="job-form">
    <input type="number" v-model="store.selectedId" placeholder="Job ID" />
    <input type="text" v-model="store.selectedTitle" placeholder="Job Title" />
    <input type="text" v-model="store.selectedCompany" placeholder="Company" />
    <input type="text" v-model="store.selectedLocation" placeholder="Location" />
    <textarea v-model="store.selectedDescription" placeholder="Description"></textarea>
    <button type="button" @click="onClickJob" class="button">Add Job</button>
  </form>
  <p v-for="job in jobs" :key="job.id">
    <strong>{{ job.title }}</strong> at {{ job.company }} in {{ job.location }}
    <br />
    {{ job.description }}
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
