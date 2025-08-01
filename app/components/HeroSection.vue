<template>
  <section class="relative">
    <Swiper :modules="[Autoplay]" autoplay loop class="h-[60vh] w-full">
      <SwiperSlide v-for="(img, i) in images" :key="i">
        <img :src="img" alt="banner" class="object-cover w-full h-full" />
      </SwiperSlide>
    </Swiper>
  </section>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Autoplay } from "swiper/modules";
import "swiper/css";
const images = ["/banner1.jpg", "/banner2.jpg"];
</script>
