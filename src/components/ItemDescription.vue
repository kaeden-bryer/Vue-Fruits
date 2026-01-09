<script setup lang="ts">

defineProps<{
  name: string
  description: string
  image: string
}>()

</script>

<template>
    <div class="item-description">
        <h2>{{ name }}</h2>
        <img :src="image" :alt="name" />
        <p>{{ description }}</p>
    </div>
</template>

<style scoped>

.item-description {
    display: flex;
    flex-direction: column;
    justify-self: center;
    justify-content: center;
    align-items: center;
    width: 70vw;
    height: 70vh;
    background: lightgreen;
}

img {
    height: 20em;
    width: 20em;
    border-radius: 15px;
}
</style>