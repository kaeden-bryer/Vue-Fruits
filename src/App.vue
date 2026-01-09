<script setup lang="ts">
import ItemDescription from './components/ItemDescription.vue';
import Menu from './components/Menu.vue'
import { ref } from 'vue'

const toggleItemDescription = ref(false)
const selectedItem = ref<{ name: string, description: string, image: string } | null>(null)

const handleItemClick = (itemData: { name: string; description: string; image: string }) => {
  selectedItem.value = itemData;
  toggleItemDescription.value = true;
};

const closeItemDescription = () => {
  toggleItemDescription.value = false;
  selectedItem.value = null;
};
</script>

<template>
  <Menu @item-clicked="handleItemClick" />
  <div class="item-description-container" v-if="toggleItemDescription && selectedItem">
    <div class="item-description-overlay" @click="closeItemDescription"></div>
    <ItemDescription 
      :name="selectedItem.name"
      :description="selectedItem.description"
      :image="selectedItem.image"
    />
  </div>

</template>

<style scoped>

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

.item-description-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.item-description-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.7);
  z-index: -1;
}

</style>
