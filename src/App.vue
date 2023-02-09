<script setup>

import { RouterView, useRouter } from "vue-router";
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';
const router = useRouter()

</script>

<template>
  <div class="box-border antialiased">
    <Navbar v-if="router.currentRoute.value.name !== 'login'"  />
    <RouterView /> 
    <Footer />
  </div>
</template>
