<script setup lang="ts">

defineProps<{
    image: string,
    bgColor: string
}>()
</script>

<template>
    <img :src="image" :style="{ '--color': bgColor }" class="menu-item" />
</template>

<style scoped>
.menu-item {
  height: 15em;
  will-change: filter;
  transition: filter 300ms;
  border-radius: 20px;
}
.menu-item:hover {
  filter: drop-shadow(0 0 2em var(--color));
  transform: scale(1.05);
  transition: transform 200ms ease-in-out;
}
</style>