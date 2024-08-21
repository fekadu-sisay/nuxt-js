<template>
  <div>
    <head>
      <Title>Nuxt 3 - Iphone {{ name }}</Title>
    </head>
    <div class="flex justify-center w-full mt-20">
      <div class="grid grid-cols-2">
        <div>
          <img :src="`/images/iphone${name}.webp`" class="h-96 object-cover" />
        </div>
        <div class="text-center">
          <h1 class="text-3xl">Iphone {{ $route.params.name }}</h1>
          <button
            @click="addToCart"
            class="p-3 bg-indigo-900 text-white rounded-md mt-5 w-48"
          >
            <span v-if="isInCart">Remove from Cart</span>
            <span v-else>Buy Now</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const route = useRoute();
const cart = useCart();

const name = computed(() => {
  return route.params.name.replaceAll("-", "");
});

const fullname = computed(() => `iphone-${route.params.name}`);

const isInCart = computed(
  () => !!cart.value.find((item) => item.name === fullname.value)
);

const addToCart = () => {
  if (!isInCart.value) {
    cart.value.push({
      name: fullname.value,
    });
  } else {
    cart.value = cart.value.filter((item) => item.name !== fullname.value);
  }
};
</script>
