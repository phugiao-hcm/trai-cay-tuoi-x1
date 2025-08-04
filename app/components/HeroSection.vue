<template>
    <section class="relative">
        <Swiper
            :modules="[Autoplay]"
            :autoplay="{ delay: 4000 }"
            loop
            class="w-full"
        >
            <SwiperSlide v-for="(slide, i) in slides" :key="i">
                <div class="relative w-full">
                    <!-- Hình ảnh full màn hình ngang, cao auto hoặc tối thiểu 400px -->
                    <img
                        :src="slide.image"
                        alt="Banner"
                        class="w-full h-[60vh] object-cover"
                    />

                    <!-- Overlay chữ -->
                    <div
                        class="absolute inset-0 bg-black/40 flex flex-col justify-center items-center text-center text-white px-4"
                    >
                        <h2 class="text-3xl md:text-5xl font-bold">
                            {{ slide.title }}
                        </h2>
                        <p class="mt-3 text-lg md:text-xl">
                            {{ slide.subtitle }}
                        </p>
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

const slides = [
    {
        image: "images/hero_1.png",
        title: "Trái cây nhập khẩu cao cấp",
        subtitle: "Chất lượng tươi ngon – Giao nhanh toàn quốc",
    },
    {
        image: "images/hero_2.png",
        title: "100% hàng chính ngạch",
        subtitle: "Nguồn gốc rõ ràng, đạt chuẩn an toàn thực phẩm",
    },
    {
        image: "images/hero_3.png",
        title: "Ưu đãi hấp dẫn mỗi ngày",
        subtitle: "Mua càng nhiều – Giảm càng sâu",
    },
];
</script>
