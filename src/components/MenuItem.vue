<script setup lang="ts">

const props = defineProps<{
    image: string,
    name: string,
    description: string,
    bgColor: string
}>()

const emit = defineEmits<{
  (e: 'item-clicked', data: { name: string, description: string, image: string }): void
}>()

const handleClick = () => {
  emit('item-clicked', {
    name: props.name,
    description: props.description,
    image: props.image
  })
}
</script>

<template>
    <img :src="image" :style="{ '--color': bgColor }" class="menu-item" @click="handleClick" />
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