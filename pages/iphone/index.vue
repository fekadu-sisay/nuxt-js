<template>
  <div class="grid grid-cols-4 gap-4 mt-10">
    <nuxt-link
      to="/iphone/iphone-12"
      class="shadow-lg broder rounded-lg text-center"
    >
      <h1>Iphone 12</h1>
      <div class="flex justify-center">
        <img width="200" src="/images/iphone12.webp" alt="" />
      </div>
    </nuxt-link>

    <nuxt-link
      to="/iphone/iphone-12-pro"
      class="shadow-lg broder rounded-lg text-center"
    >
      <h1>Iphone 12 Pro</h1>
      <div class="flex justify-center">
        <img width="200" src="/images/iphone12pro.webp" alt="" />
      </div>
    </nuxt-link>
  </div>
</template>

<script setup>
useHead({
  title: "Nuxt3 - Iphones",
});
</script>
