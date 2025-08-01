<template>
  <section class="py-10">
    <div class="container mx-auto px-4">
      <!-- Flash Sale Header -->
      <div class="flex items-center justify-between mb-6">
        <div class="flex items-center gap-2">
          <img src="/images/1.png" alt="flash" class="w-6 h-6" />
          <h2 class="text-2xl font-bold text-red-600">FLASH SALE</h2>
          <div class="flex gap-1 text-white text-sm font-semibold ml-4">
            <div
              v-for="(t, i) in timeParts"
              :key="i"
              class="bg-red-600 px-2 py-1 rounded"
            >
              {{ t.value }}<br />
              <span class="text-xs">{{ t.label }}</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Swiper Products -->
      <Swiper
        :slides-per-view="1.5"
        :breakpoints="{
          640: { slidesPerView: 1.5 },
          768: { slidesPerView: 3 },
          1024: { slidesPerView: 5.5 },
        }"
        space-between="20"
        navigation
        class="overflow-hidden"
      >
        <SwiperSlide v-for="prod in products" :key="prod.id">
          <div
            class="border rounded-lg overflow-hidden bg-white hover:shadow-lg transition"
          >
            <div class="relative">
              <img :src="prod.image" class="w-full h-52 object-cover" />
              <div
                v-if="prod.discount"
                class="absolute top-2 left-2 bg-red-600 text-white text-xs font-bold px-2 py-1 rounded"
              >
                -{{ prod.discount }}%
              </div>
            </div>
            <div class="p-3 text-center">
              <p class="text-sm text-gray-400">{{ prod.origin }}</p>
              <h3 class="font-semibold text-sm line-clamp-2">
                {{ prod.name }}
              </h3>
              <p class="text-red-600 font-bold">
                {{ prod.price }}
                <span class="text-gray-400 line-through ml-1 text-sm">{{
                  prod.oldPrice
                }}</span>
              </p>
              <button
                class="border mt-3 px-4 py-2 text-sm font-medium rounded w-full hover:bg-purple-100"
              >
                🛍️ CHỌN MUA
              </button>
            </div>
          </div>
        </SwiperSlide>
      </Swiper>
    </div>
  </section>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/navigation";
import { Navigation } from "swiper/modules";
import { ref, onMounted } from "vue";

const products = [
  {
    id: 1,
    name: "Nho Kẹo Candy Snaps Mỹ",
    price: "349,000₫ - 1,398,000₫",
    oldPrice: "1,399,000₫",
    discount: 13,
    image: "/products/nho-candy.jpg",
    origin: "MỸ",
  },
  {
    id: 2,
    name: "Nho Shine Muscat Hàn Quốc VIP",
    price: "1,499,000₫ - 4,718,000₫",
    oldPrice: "1,802,000₫",
    discount: 17,
    image: "/products/nho-shine.jpg",
    origin: "HÀN QUỐC",
  },
  {
    id: 2,
    name: "Nho Shine Muscat Hàn Quốc VIP",
    price: "1,499,000₫ - 4,718,000₫",
    oldPrice: "1,802,000₫",
    discount: 17,
    image: "/products/nho-shine.jpg",
    origin: "HÀN QUỐC",
  },
  {
    id: 2,
    name: "Nho Shine Muscat Hàn Quốc VIP",
    price: "1,499,000₫ - 4,718,000₫",
    oldPrice: "1,802,000₫",
    discount: 17,
    image: "/products/nho-shine.jpg",
    origin: "HÀN QUỐC",
  },
  {
    id: 2,
    name: "Nho Shine Muscat Hàn Quốc VIP",
    price: "1,499,000₫ - 4,718,000₫",
    oldPrice: "1,802,000₫",
    discount: 17,
    image: "/products/nho-shine.jpg",
    origin: "HÀN QUỐC",
  },
  {
    id: 2,
    name: "Nho Shine Muscat Hàn Quốc VIP",
    price: "1,499,000₫ - 4,718,000₫",
    oldPrice: "1,802,000₫",
    discount: 17,
    image: "/products/nho-shine.jpg",
    origin: "HÀN QUỐC",
  },
];

const countdown = ref(36000); // seconds
const timeParts = ref([]);

const updateCountdown = () => {
  const hours = Math.floor(countdown.value / 3600);
  const minutes = Math.floor((countdown.value % 3600) / 60);
  const seconds = countdown.value % 60;
  timeParts.value = [
    { label: "Giờ", value: String(hours).padStart(2, "0") },
    { label: "Phút", value: String(minutes).padStart(2, "0") },
    { label: "Giây", value: String(seconds).padStart(2, "0") },
  ];
};

onMounted(() => {
  updateCountdown();
  setInterval(() => {
    if (countdown.value > 0) {
      countdown.value--;
      updateCountdown();
    }
  }, 1000);
});
</script>

<style scoped>
.line-clamp-2 {
  overflow: hidden;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}
</style>
