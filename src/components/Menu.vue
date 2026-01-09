<script setup lang="ts">
import MenuItem from './MenuItem.vue'
import data from '../data.json'

const emit = defineEmits<{
  (e: 'item-clicked', data: { name: string, description: string, image: string }): void
}>()

const handleItemClick = (itemData: { name: string, description: string, image: string }) => {
  emit('item-clicked', itemData)
}
</script>

<template>
    <h1>Fruits Menu!🍉</h1>
    <div class="menu">
      <MenuItem
        v-for="fruit in data" :key="fruit.name"
        :image="fruit.image"
        :name="fruit.name"
        :description="fruit.description"
        :bgColor="fruit.bgColor"
        @item-clicked="handleItemClick"
      />
    </div>
</template>

<style scoped>

.menu {
  display: flex;
  width: 80vw;
  flex-direction: row;
  flex-wrap: wrap;
  justify-self: center;
  background: pink;
  justify-content: center;
  gap: 2em 2em;
  padding: 2em;
}

</style>