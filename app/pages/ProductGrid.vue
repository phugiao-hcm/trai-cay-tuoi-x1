<template>
    <div class="max-w-[1200px] mx-auto px-4">
        <section class="px-4 py-8">
            <!-- Tiêu đề -->
            <h2 class="text-xl font-bold mb-4">Sản phẩm nổi bật</h2>

            <!-- Lưới sản phẩm -->
            <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 gap-4">
                <div
                    v-for="prod in products"
                    :key="prod.id"
                    class="rounded-lg overflow-hidden shadow hover:shadow-lg transition bg-white"
                >
                    <!-- Ảnh sản phẩm -->
                    <img
                        :src="prod.image"
                        :alt="prod.name"
                        class="w-full h-40 object-cover"
                    />

                    <!-- Thông tin -->
                    <div class="p-3">
                        <h3 class="text-sm font-semibold line-clamp-2">
                            {{ prod.name }}
                        </h3>
                        <p class="text-red-500 font-bold mt-1">
                            {{ prod.price }}
                        </p>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>


<script setup>
const products = [
    {
        id: 1,
        name: "Thứ 2 Sống Lành Mỗi Ngày - Sống Sang Cùng Klever Fruit",
        price: "349.000₫",
        image: "images/noi_bat_1.png",
    },
    {
        id: 2,
        name: "Thứ 3 Sống Lành Mỗi Ngày - Sống Sang Cùng Klever Fruit",
        price: "199.000₫",
        image: "images/noi_bat_2.png",
    },
    {
        id: 3,
        name: "Thứ 4 Sống Lành Mỗi Ngày - Sống Sang Cùng Klever Fruit",
        price: "199.000₫",
        image: "images/noi_bat_3.png",
    },
    {
        id: 4,
        name: "Thứ 5 Sống Lành Mỗi Ngày - Sống Sang Cùng Klever Fruit",
        price: "199.000₫",
        image: "images/noi_bat_4.png",
    },
];
</script>
