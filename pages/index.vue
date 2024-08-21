<template>
  <div>
    <h1>Hello Index</h1>
    <button @click="moveToAbout()">Take me to about page</button>
  </div>
</template>

<script setup>
const moveToAbout = () => {
  navigateTo("about");
};
</script>
