<template>
  <div>
    <NuxtPage />
    <a href="#" @click="view('home')">Home</a>
    <a href="#" @click="view('counter')">Counter</a>

    <LazyHomeWelcome v-if="page === 'home'" />
    <LazyCounter v-if="page === 'counter'" />
  </div>
</template>

<script setup>
const page = ref("home");

const view = (name) => {
  page.value = name;
};
</script>
