<script setup>

import { RouterView } from "vue-router";
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';

</script>

<template>
  <div class="box-border antialiased bg-gray-200">
    <Navbar />
    <RouterView /> 
    <Footer />
  </div>
</template>
