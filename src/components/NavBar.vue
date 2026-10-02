<script setup>
import { ref } from "vue";

const isOpen = ref(false);
const navLinks = [
  { name: "Home", to: "#home" },
  { name: "About", to: "#about" },
  { name: "Skills", to: "#skills" },
  { name: "Work", to: "#work" },
  { name: "Experience", to: "#experience" },
  { name: "Contact", to: "#contact" },
];
const closeMenu = () => {
  isOpen.value = false;
};

<template>
  
</template>;
</script>
