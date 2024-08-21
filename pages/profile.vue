<template>
  <p>Welcome John</p>
</template>

<script setup>
definePageMeta({
  layout: "sidebar",
  middleware: ["auth"],
});
</script>
