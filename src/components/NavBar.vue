<script setup>
import { ref } from "vue";

const isOpen = ref(false);

const navLinks = [
  { name: "About-me?", to: "#about" },
  { name: "Work", to: "#work" },
  { name: "Experience", to: "#experience" },
  { name: "Contact", to: "#contact" },
];

const closeMenu = () => {
  isOpen.value = false;
};
</script>

<template>
  <nav class="relative border-b border-gray-200 bg-white">
    <div class="mx-auto flex max-w-6xl items-center justify-between px-6 py-4">
      <span class="rounded-md border border-gray-300 px-3 py-1 text-lg font-bold text-gray-900">KHUNPON</span>

      <ul class="hidden gap-8 text-sm font-medium text-gray-500 md:flex">
        <li v-for="link in navLinks" :key="link.to">
          <a :href="link.to" class="inline-block transition hover:scale-125 hover:text-black">
            {{ link.name }}
          </a>
        </li>
      </ul>

      <button class="flex h-8 w-10 flex-col items-center justify-center gap-1.5 md:hidden" @click="isOpen = !isOpen"
        aria-label="เปิด/ปิดเมนู">
        <span class="block h-0.5 w-6 bg-gray-900 transition" :class="isOpen && 'translate-y-2 rotate-45'"></span>
        <span class="block h-0.5 w-6 bg-gray-900 transition" :class="isOpen && 'opacity-0'"></span>
        <span class="block h-0.5 w-6 bg-gray-900 transition" :class="isOpen && '-translate-y-2 -rotate-45'"></span>
      </button>
    </div>

    <ul v-if="isOpen" class="flex flex-col gap-4 border-t border-gray-200 px-6 py-4 text-sm font-medium md:hidden">
      <li v-for="link in navLinks" :key="link.to">
        <a :href="link.to" class="block" @click="closeMenu">
          {{ link.name }}
        </a>
      </li>
    </ul>
  </nav>
</template>