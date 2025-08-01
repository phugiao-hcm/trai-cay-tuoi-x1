<template>
  <header class="bg-white sticky top-0 shadow">
    <div class="container mx-auto px-4 py-3 flex justify-between items-center">
      <NuxtLink to="/" class="text-2xl font-bold">KleverFruit</NuxtLink>
      <nav class="hidden md:flex space-x-6">
        <NuxtLink to="/">Trang chủ</NuxtLink>
        <NuxtLink to="/collections">Sản phẩm</NuxtLink>
        <NuxtLink to="/about">Giới thiệu</NuxtLink>
        <NuxtLink to="/contact">Liên hệ</NuxtLink>
      </nav>
      <button class="md:hidden" @click="open = !open">
        <svg>...</svg>
      </button>
    </div>
    <div v-if="open" class="md:hidden bg-white px-4 pb-4 space-y-2">
      <NuxtLink to="/">Trang chủ</NuxtLink>
      <NuxtLink to="/collections">Sản phẩm</NuxtLink>
    </div>
  </header>
</template>

<script setup>
import { ref } from "vue";
const open = ref(false);
</script>
