<template>
  <div class="grid grid-cols-4 gap-4 mt-10">
    <nuxt-link
      v-for="iphone in iphones"
      :key="iphone"
      :to="`/iphone/${iphone}`"
      class="shadow-lg broder rounded-lg text-center"
    >
      <h1>{{ iphone }}</h1>
      <div class="flex justify-center">
        <img
          width="200"
          :src="`/images/${iphone.replaceAll('-', '')}.webp`"
          alt=""
        />
      </div>
    </nuxt-link>
  </div>
</template>

<script setup>
useHead({
  title: "Nuxt3 - Iphones",
});

const { data } = useFetch("/api/iphones");
const iphones = data.value;
</script>
