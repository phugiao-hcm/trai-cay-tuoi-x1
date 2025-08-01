<template>
  <div class="max-w-[1200px] mx-auto px-4">
    <HeroSection />
    <FlashSaleSlider />
    <FlashSaleBanner />
    <ProductSection />
    <ProductGrid />
  </div>
</template>

<script setup>
import HeroSection from "@/components/HeroSection.vue";
import FlashSaleBanner from "./FlashSaleBanner.vue";
import ProductGrid from "./ProductGrid.vue";
import FlashSaleSlider from "./FlashSaleSlider.vue";
import ProductSection from "./ProductSection.vue";
</script>

