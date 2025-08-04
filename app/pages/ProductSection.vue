<template>
    <div class="max-w-[1200px] mx-auto px-4">
        <section class="py-10">
            <div class="text-center mb-8">
                <h2 class="text-3xl font-bold text-orange-500">
                    Quà tặng trái cây
                </h2>
            </div>
            <div
                class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-5"
            >
                <div
                    v-for="(item, index) in products"
                    :key="index"
                    class="border rounded-lg shadow-sm p-3 flex flex-col justify-between relative bg-white"
                >
                    <!-- Tag -->
                    <div
                        v-if="item.soldOut"
                        class="absolute top-2 left-2 bg-gray-800 text-white text-xs px-2 py-1 rounded"
                    >
                        Tạm hết hàng
                    </div>

                    <!-- Image -->
                    <img
                        :src="item.image"
                        :alt="item.name"
                        class="object-cover w-full h-40 rounded"
                    />

                    <!-- Info -->
                    <div class="mt-3">
                        <p
                            class="text-sm font-medium line-clamp-2 min-h-[40px]"
                        >
                            {{ item.name }}
                        </p>
                        <p class="text-base font-semibold text-blue-800 mt-2">
                            {{ formatPrice(item.price) }}
                        </p>
                    </div>

                    <!-- Button -->
                    <button
                        class="mt-3 w-full text-sm font-medium border rounded py-1 transition"
                        :class="
                            item.soldOut
                                ? 'bg-gray-100 text-gray-400 cursor-not-allowed'
                                : 'bg-white text-orange-500 border-orange-500 hover:bg-orange-50'
                        "
                        :disabled="item.soldOut"
                    >
                        {{ item.soldOut ? "TẠM HẾT HÀNG" : "🛍 CHỌN MUA" }}
                    </button>
                </div>
            </div>
        </section>
    </div>
</template>

<script setup>
const products = [
    {
        name: "Giỏ quà trái cây G036",
        image: "images/qua_tang_1.png",
        price: 1995000,
        soldOut: true,
    },
    {
        name: "Hộp quà trái cây HQ241",
        image: "images/qua_tang_2.png",
        price: 1295000,
        soldOut: true,
    },
    {
        name: "Bó hoa dâu tây size M",
        image: "images/qua_tang_3.png",
        price: 885000,
        soldOut: false,
    },
    {
        name: "Hộp quà trái cây HQ240",
        image: "images/qua_tang_4.png",
        price: 755000,
        soldOut: true,
    },
    {
        name: "Bó Kẹo Trái Cây Không Lộ Tone Hồng",
        image: "images/qua_tang_5.png",
        price: 285000,
        soldOut: false,
    },
];

const formatPrice = (value) => {
    return new Intl.NumberFormat("vi-VN", {
        style: "currency",
        currency: "VND",
        maximumFractionDigits: 0,
    }).format(value);
};
</script>

<style scoped>
.line-clamp-2 {
    overflow: hidden;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
}
</style>
