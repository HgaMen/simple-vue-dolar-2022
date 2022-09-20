<script setup>
import IconDarkMode from "@/components/icons/IconDarkMode.vue";
import IconLightMode from "@/components/icons/IconLightMode.vue";
import { useDarkMode } from "@/composables/useDarkMode.js";

const { changeDarkMode, toggleDarkMode } = useDarkMode();
</script>

<template>
    <header class="p-4 mb-5 text-white bg-gray-800">
        <div class="flex items-center justify-between mx-auto max-w-7xl">
            <h1
                class="text-2xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-rose-400 via-fuchsia-500 to-indigo-500"
            >
                API Dollar
            </h1>
            <button
                @click="changeDarkMode"
                class="active:ring-rose-400 hover:ring rounded-lg p-0.5 outline-none ring-indigo-500 dark:text-white"
            >
                <IconDarkMode v-if="toggleDarkMode" />
                <IconLightMode v-else />
            </button>
        </div>
    </header>
</template>
