<template>
    <header class="bg-green-50 sticky top-0 z-50 shadow-md">
        <div
            class="container mx-auto px-4 py-3 flex justify-between items-center"
        >
            <!-- Logo -->
            <NuxtLink to="/" class="text-2xl font-bold text-green-700">
                Phú Giáo Fruit
            </NuxtLink>

            <!-- Desktop Menu -->
            <nav
                class="hidden md:flex space-x-6 text-sm font-medium text-green-800"
            >
                <NuxtLink to="/" class="hover:text-green-600"
                    >Trang chủ</NuxtLink
                >
                <NuxtLink to="/" class="hover:text-green-600"
                    >Sản phẩm</NuxtLink
                >
                <NuxtLink to="/" class="hover:text-green-600"
                    >Giới thiệu</NuxtLink
                >
                <NuxtLink to="/" class="hover:text-green-600">Liên hệ</NuxtLink>
            </nav>

            <!-- Hamburger -->
            <button
                class="md:hidden text-green-800"
                @click="open = !open"
                aria-label="Menu"
            >
                <svg
                    v-if="!open"
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-6 w-6"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                >
                    <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M4 6h16M4 12h16M4 18h16"
                    />
                </svg>
                <svg
                    v-else
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-6 w-6"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                >
                    <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M6 18L18 6M6 6l12 12"
                    />
                </svg>
            </button>
        </div>

        <!-- Mobile Menu -->
        <div
            v-if="open"
            class="md:hidden bg-green-50 px-4 pb-4 space-y-2 border-t border-green-100 animate-slide-down"
        >
            <NuxtLink to="/" class="block text-green-800 hover:text-green-600"
                >Trang chủ</NuxtLink
            >
            <NuxtLink to="/" class="block text-green-800 hover:text-green-600"
                >Sản phẩm</NuxtLink
            >
            <NuxtLink to="/" class="block text-green-800 hover:text-green-600"
                >Giới thiệu</NuxtLink
            >
            <NuxtLink to="/" class="block text-green-800 hover:text-green-600"
                >Liên hệ</NuxtLink
            >
        </div>
    </header>
</template>

<script setup>
import { ref } from "vue";
const open = ref(false);
</script>

<style scoped>
@keyframes slide-down {
    0% {
        opacity: 0;
        transform: translateY(-8px);
    }
    100% {
        opacity: 1;
        transform: translateY(0);
    }
}
.animate-slide-down {
    animation: slide-down 0.2s ease-out;
}
</style>
