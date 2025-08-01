<template>
  <section class="relative overflow-hidden">
    <Swiper :modules="[Autoplay]" :autoplay="{ delay: 4000 }" :loop="true">
      <SwiperSlide v-for="(img, i) in slides" :key="i">
        <div
          class="relative h-[60vh] bg-cover bg-center"
          :style="{ backgroundImage: `url(${img})` }"
        >
          <div class="absolute inset-0 bg-black/40"></div>
          <div
            class="absolute inset-0 flex flex-col justify-center text-center text-white px-4"
          >
            <h2 class="text-3xl md:text-5xl font-bold">
              {{ captions[i].title }}
            </h2>
            <p class="mt-3 text-lg">{{ captions[i].subtitle }}</p>
          </div>
        </div>
      </SwiperSlide>
    </Swiper>
  </section>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Autoplay } from "swiper/modules";
import "swiper/css";

const slides = ["/images/slide1.jpg", "/images/slide2.jpg"];
const captions = [
  {
    title: "Shop Hoa Tươi Gò Vấp",
    subtitle: "Dịch vụ giao hoa nhanh 60–90 phút",
  },
  {
    title: "Thiết kế hoa theo yêu cầu",
    subtitle: "Tặng thiệp & banner miễn phí",
  },
];
</script>
