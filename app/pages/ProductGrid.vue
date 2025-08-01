<template>
  <section class="px-4 py-8">
    <h2 class="text-xl font-bold mb-4">Sản phẩm nổi bật</h2>
    <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 gap-4">
      <div
        v-for="prod in products"
        :key="prod.id"
        class="border rounded-lg overflow-hidden shadow hover:shadow-lg transition bg-white"
      >
        <img
          :src="prod.image"
          alt="prod.name"
          class="w-full h-40 object-cover"
        />
        <div class="p-2">
          <h3 class="text-sm font-semibold">{{ prod.name }}</h3>
          <p class="text-red-500 font-bold">{{ prod.price }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const products = [
  { id: 1, name: "Nho Mỹ", price: "349.000₫", image: "/prod1.jpg" },
  { id: 2, name: "Táo New Zealand", price: "199.000₫", image: "/prod2.jpg" },
  // thêm sản phẩm...
];
</script>
