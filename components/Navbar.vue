<template>
  <nav
    class="bg-purple-900 text-white text-lg flex shadow-lg p-3 justify-between"
  >
    <div class="flex">
      <NuxtLink class="mr-4" to="/">Home</NuxtLink>
      <NuxtLink class="mr-4" to="/iphone">Iphones</NuxtLink>

      <p class="mr-4">Cart ({{ cart.length }})</p>
      <p>Total Route Changed : {{ pageVisitCount }}</p>
    </div>

    <div v-if="auth.isAuthenticated">
      <NuxtLink to="/profile">Profile</NuxtLink>
      <button class="ml-4" @click="logout">Logout</button>
    </div>

    <NuxtLink to="/login" v-else>Login</NuxtLink>
  </nav>
</template>

<script setup>
const cart = useCart();
const auth = useAuth();
const pageVisitCount = usePageVisitCount();

const logout = () => {
  auth.value.isAuthenticated = false;
};
</script>
