<script setup>
import { RouterView } from "vue-router";
import Navbar from './components/Navbar.vue';
</script>

<template>
  <div class="box-border antialiased bg-gray-200">
    <Navbar />
    <RouterView /> 
  </div>
</template>
